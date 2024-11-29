# High-Traffic Recipe Predictor

This repository contains the code and analysis for predicting high-traffic recipes using an ensemble model. The project aims to assist the Product Team in promoting recipes likely to generate substantial user engagement, thereby optimizing site traffic and user satisfaction.

---

## **Project Overview**

### **Objective**
To classify recipes as "High Traffic" or "Not High Traffic" based on features like calories, macronutrient composition, and category. This classification helps prioritize recipes with high engagement potential.

### **Dataset**
The dataset includes:
- **Recipe**: Unique identifier for each recipe.
- **Calories, Carbohydrate, Sugar, Protein**: Nutritional information.
- **Category**: Recipe type (e.g., Dessert, Main Course).
- **Servings**: Number of servings per recipe.
- **High Traffic**: Target variable indicating whether a recipe is high traffic.

---

## **Workflow**

### **1. Data Validation**
- Verified and cleaned each column:
  - Replaced missing values with statistical imputations (e.g., median for numerical columns, mode for categorical columns).
  - Standardized categorical values (e.g., consistent labels for "Dessert").
  - Handled outliers using IQR method.
  
### **2. Exploratory Data Analysis (EDA)**
- Visualized the distribution of single variables (e.g., calories and categories).
- Explored relationships between features (e.g., protein vs. high traffic) using scatter plots and box plots.

### **3. Model Development**
- **Baseline Model**: Logistic Regression
- **Comparison Model**: Voting Classifier (combines Logistic Regression, Random Forest, CART, and LightGBM).
- Implemented models using scikit-learn, focusing on precision as the key performance metric.

### **4. Model Evaluation**
- **Baseline Model**:
  - Precision: 72%, F1 Score: 70%
- **Voting Classifier**:
  - Precision: 80%, F1 Score: 79%, ROC-AUC: 84.5%
- The Voting Classifier significantly outperformed the baseline model.

### **5. Business Recommendations**
- Deploy the Voting Classifier to improve the accuracy of recipe promotion.
- Conduct A/B testing to measure real-world impact on user engagement.
- Enhance dataset with additional features like preparation time and user ratings.

---

## **Repository Structure**

```plaintext
├── data/
│   ├── recipe_site_traffic_2212.csv                # Original dataset
├── notebooks/
│   # Data cleaning and validation
│   # Exploratory data analysis
│   # Model development and evaluation
├── results/
│   # Predictions from Logistic Regression
│   # Predictions from Voting Classifier
├── requirements.txt               # Required Python libraries
├── README.md                      # Project documentation
