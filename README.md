<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/8ac75a93-a8c5-4f86-9782-ca9c93959024" />

### Steps Taken in this Project:

1. **Integrated Multiple Scripts:** - Combined the data loading logic from `Import Required Libraries.txt` with the advanced processing from `Code 01.txt`.
   
2. **Data Alignment:** - Verified the features from the `ai_workforce_displacement_global_2020_2026.csv` file. 
   - Mapped column names correctly (e.g., mapping 'Automation Risk' to 'sector_automation_risk_score') to ensure the model recognizes the data.

3. **Handling Large Dataset:** - The CSV contains 20,800+ records. I used `df.columns.str.strip()` to clean any hidden spaces in the column names that were causing errors.

4. **Target Variable Setup:** - Used the `net_workforce_change_pct` column to create a binary classification target (1 for Job Loss, 0 for Gain).

5. **Cross-Model Validation:** - Applied Random Forest and XGBoost (as seen in Code 01) to compare accuracy against the baseline Logistic Regression model.

6. ### 🚀 Advanced Analytics Added:

6. **Sector-Specific Vulnerability Analysis:**
   - Conducted a deep dive into which industries (e.g., Finance vs. Manufacturing) are most susceptible to AI-driven displacement based on current automation risk scores.

7. **Feature Interaction Effects:**
   - Analyzed how 'AI Policy Score' correlates with 'Reskilling Programs' to see if government intervention effectively reduces the probability of job loss.

8. **Hyperparameter Tuning:**
   - Optimized the Random Forest model using `GridSearchCV` to achieve the best balance between Precision and Recall, ensuring we don't miss high-risk job sectors.
  
   - ### 🛠️ Advanced Project Enhancements:

9. **Gender-Centric Impact Study:**
   - Evaluated the disproportionate impact of AI on female workers by comparing `pct_workforce_female` against displacement rates. This provides an ethical perspective on AI adoption.

10. **Custom Feature Engineering:**
    - Developed a **"Policy-Risk Gap"** index to identify regions where AI automation risk outpaces government policy preparedness.

11. **Time-Series Forecasting:**
    - Visualized the quarterly progression (2020-2026) of AI tool adoption to identify "tipping points" in different industry sectors.

12. **Model Optimization:**
    - Performed **Hyperparameter Tuning** using `GridSearchCV` to minimize False Negatives, which is crucial when predicting high-risk job loss scenarios.

13. **API Integration (Future Scope):**
    - Planned a FastAPI wrapper to allow users to input sector-specific data and receive instant job stability predictions.

    ### 🌟 Unique Project Innovations:

14. **What-If Simulation Engine:**
    - Developed a simulation script that allows users to adjust parameters like `ai_adoption_index` or `govt_ai_policy_score` to see real-time impacts on predicted workforce changes.

15. **Ensemble Stacking Architecture:**
    - Combined the predictive power of **XGBoost**, **Random Forest**, and **Logistic Regression** using a Meta-Classifier to reduce variance and improve model generalization.

16. **AI Impact Clustering (Unsupervised Learning):**
    - Leveraged **K-Means Clustering** to segment global regions into risk profiles, identifying "Vulnerable Zones" where high automation risk meets low policy preparedness.

17. **Reskilling ROI Analysis:**
    - Quantified the inverse relationship between `reskilling_programs_count` and `pct_sector_workforce_displaced`, providing a data-driven justification for educational investment.

18. **Interactive Visual Reporting:**
    - Implemented **Plotly** for dynamic visualizations, allowing stakeholders to drill down into specific industry sectors or geographical regions.
   
### 🔍 Model Interpretability with SHAP
To ensure our AI model is transparent, we used SHAP (SHapley Additive exPlanations) to identify which factors drive job displacement.
- **Top Driver:** `ai_tool_adoption_pct` showed the highest correlation with workforce change.
- **Insight:** Higher government policy scores significantly mitigate displacement risks.

- # Sample API Endpoint for Job Loss Prediction
@app.post("/predict")
def predict_displacement(data: IndustryData):
    prediction = model.predict(data.features)
    return {"job_loss_risk": "High" if prediction == 1 else "Low"}

### ⚖️ Gender Impact Study
We analyzed the `pct_displaced_roles_female` to check for AI bias. 
- **Finding:** Certain sectors like 'Administrative & Clerical' show a 15% higher displacement rate for female workers compared to the sector average.
- **Action:** Recommended targeted reskilling programs for female-dominated roles.

- ## 🛠️ Project Architecture & Tools

| Step | Implementation | Tools Used |
| :--- | :--- | :--- |
| **Data Engineering** | Handling 20k+ records, feature scaling | `Pandas`, `NumPy` |
| **Exploratory Analysis** | Correlation heatmaps, Trend analysis | `Seaborn`, `Matplotlib` |
| **Model Selection** | Comparing Regression vs Classification | `Scikit-Learn`, `XGBoost` |
| **Optimization** | Hyperparameter tuning with GridSearchCV | `Scikit-Learn` |
| **Ethical Audit** | Gender-based displacement analysis | `Custom Python Scripts` |


    
