# 📊 Telecom Customer Churn Prediction

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

פרויקט מקצה-לקצה ב-Machine Learning לחיזוי נטישת לקוחות בחברת תקשורת, זיהוי גורמי הסיכון המרכזיים ופיתוח תובנות עסקיות לשימור לקוחות.

---

## 📌 סקירת הפרויקט והבעיה העסקית
נטישת לקוחות (Churn) היא אחד האתגרים המרכזיים בחברות תקשורת, שכן עלות גיוס לקוח חדש גבוהה משמעותית משימור לקוח קיים. 
מטרת הפרויקט היא לבנות מודל סיווג המסוגל לזהות בסבירות גבוהה לקוחות בסכנת נטישה (מתן דגש על **Recall** גבוה כדי למזער False Negatives), תוך ניתוח המשתנים המשפיעים ביותר על החלטת הלקוח.

---

## 🛠️ טכנולוגיות וכלים
* **שפת פיתוח:** Python
* **עיבוד וניתוח נתונים:** Pandas, NumPy
* **ויזואליזציה:** Matplotlib, Seaborn
* **למידת מכונה:** Scikit-Learn (Logistic Regression, Random Forest, Gradient Boosting, Naive Bayes, Decision Trees, KNN, SVM)

---

## 🔄 שלבי העבודה (Pipeline)
1. **ניקוי והכנת הנתונים (Data Preprocessing):**
   * טיפול בערכים חסרים וכפילויות.
   * המרת משתנים קטגוריאליים באמצעות One-Hot Encoding (`drop_first=True`).
   * נרמול וסיווג משתנים נומריים (`StandardScaler`).
2. **ניתוח נתונים חוקר (EDA):**
   * זיהוי מתאמים (Correlations) בין תכונות הלקוח להסתברות הנטישה.
   * ניתוח התפלגות תשלומים חודשיים, סוגי חוזים ושירותים נלווים.
3. **בנייה והשוואת מודלים:**
   * אימון 8 מודלים שונים על נתוני `Train` והערכה על `Test`.
   * טיפול בחוסר איזון במחלקה (Class Imbalance) באמצעות משקלים (`class_weight='balanced'`).
4. **הערכת ביצועים:**
   * ניתוח מדדי Precision, Recall, F1-Score ו-ROC-AUC.

---

## 📈 השוואת ביצועי מודלים

| Model | Precision | Recall | F1-Score | ROC-AUC |
| :--- | :---: | :---: | :---: | :---: |
| **Logistic Regression (Balanced)** | **0.291** | **0.520** | **0.374** | **0.514** |
| **Naive Bayes** | 0.285 | 0.440 | 0.346 | 0.530 |
| **Random Forest** | 0.267 | 0.240 | 0.253 | 0.513 |
| **Decision Tree** | 0.247 | 0.420 | 0.311 | 0.490 |

> **הערה:** המודל המוביל שנבחר הוא **Logistic Regression** בשל מדד ה-Recall הגבוה ביותר (0.520), המאפשר לחברה לזהות את מרבית הלקוחות שבסכנת נטישה.

---

## 💡 ממצאים עיקריים (Feature Importances)
* **גורמים מגבירי נטישה:** 
  * מחיר חודשי גבוה (`MonthlyCharges`).
  * חיבור לתשתית סיבים אופטיים (`InternetService_Fiber optic`).
  * מנוי חודשי מתחדש (`Contract_Month-to-month`).
* **גורמים מעכבי נטישה:**
  * וותק הלקוח בחברה (`tenure`).
  * הצטרפות לשירותי אבטחה מקוונים (`OnlineSecurity_Yes`).

---

## 🚀 התקנה והרצה

### דרישות מוקדמות
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
