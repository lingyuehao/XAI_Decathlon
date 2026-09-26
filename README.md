# XAI_Decathlon

# XAI Decathlon – SHAP

This is my notebook for the XAI Decathlon assignment. I used **SHAP** as my one method for all 10 events.

- Tabular model (random forest): `shap.TreeExplainer`
- Image model (small CNN): `shap.GradientExplainer`

## How to run

1. Open `xai_decathlon_shap.ipynb` in Colab or Jupyter.
2. Run all cells from top to bottom. The first SHAP cell installs `shap` if it's not already there.
3. It runs on CPU and takes a few minutes. The image SHAP part (Event 3) is the slowest.

I used Python 3.12 and shap 0.51.0.

## Results

| Event | Medal |
|---|---|
| 1. Most Important Feature | Gold |
| 2. One Specific Prediction | Gold |
| 3. Dataset Bias or Shortcut | Gold |
| 4. Global Feature Effect | Silver |
| 5. Compare Two Predictions | Gold |
| 6. Feature Interactions | Silver |
| 7. Where Is the Model Looking? | Gold |
| 8. Explain a Failure | Silver |
| 9. Estimate Trustworthiness | Silver |
| 10. Reverse Engineer Strategy | Silver |

The full results table with evidence and notes is at the top of the notebook. The reflection questions are at the bottom.

## Main findings

- The tabular model mostly uses `debt_ratio`, `recent_late_payments` and `zip_proxy`. `zip_proxy` being that important looks like a fairness problem.
- The image model basically ignores the shape and just looks for the red marker in the top left corner. That's why its test accuracy is about 50%.
- SHAP worked best for "why did the model predict this" questions. It was weaker for what-if, interaction and trust questions.
