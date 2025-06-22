"# Task 1" 


# 🌸 Iris Species Classification using Scikit-learn

This project demonstrates the use of **classical machine learning techniques** to classify iris flower species based on their morphological features using the **Iris dataset**. The goal is to preprocess the data, visualize key insights, train a **Decision Tree Classifier**, and evaluate the model using multiple metrics.

---

##  Dataset Description

- **Source:** UCI Machine Learning Repository / R.A. Fisher's 1936 paper  
- **Classes:** 3 species — *Iris-setosa*, *Iris-versicolor*, *Iris-virginica*  
- **Samples per class:** 50  
- **Total samples:** 150  
- **Features:**
  - SepalLengthCm
  - SepalWidthCm
  - PetalLengthCm
  - PetalWidthCm

---

## 🔧 1. Data Preprocessing

### ✅ 1.1 Handling Missing Values
No missing values were found in the dataset:

```python
df.isnull().sum()
```

### ✅ 1.2 Column Data Types
```python
df.dtypes
```

### ✅ 1.3 Removing Unnecessary Columns
We removed the `Id` column as it does not contribute to model learning:

```python
df2 = df[[col for col in df.columns if col != 'Id']]
```

### ✅ 1.4 Label Encoding
The `Species` column (categorical) was encoded into numerical values using `LabelEncoder`:

```python
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
df2['EncodedSpecies'] = le.fit_transform(df2['Species'])
df2 = df2.drop(columns=['Species'])
```

| Species         | Encoded |
|-----------------|---------|
| Iris-setosa     | 0       |
| Iris-versicolor | 1       |
| Iris-virginica  | 2       |

---

## 📊 2. Exploratory Data Analysis (EDA)

### 📦 2.1 Boxplot Analysis

```python
fig, axes = plt.subplots(2, 2, figsize=(10, 10))
columns_to_plot = ['SepalLengthCm', 'SepalWidthCm', 'PetalLengthCm', 'PetalWidthCm']
for i, col in enumerate(columns_to_plot):
    sns.boxplot(data=df2[col], ax=axes[i//2][i%2])
    axes[i//2][i%2].set_title(f"Boxplot of {col}")
plt.tight_layout()
plt.show()
```

📍 **Observation:**
- `SepalWidthCm` has visible **outliers**.
- Other features show relatively symmetric distributions.

### 🔥 2.2 Kendall Correlation Heatmap

```python
plt.figure(figsize=(10,10))
sns.heatmap(df2.corr(method='kendall'), cbar=True, square=True, fmt='.1f', 
            annot=True, annot_kws={'size':8}, cmap='Blues')
plt.title('Correlation Heatmap', fontsize=18, pad=12)
```

📌 **Key Insights:**
- Strong positive correlation between `PetalLengthCm` and `PetalWidthCm`
- `SepalWidthCm` has low or negative correlation with other features

---

## 🤖 3. Model Training

### 🧠 3.1 Model: Decision Tree Classifier
*(Coming soon or in progress...)*

---

## 📏 4. Evaluation Metrics

(Planned or pending...)

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

---

## 📈 5. Visualizations

- ✅ Boxplots  
- ✅ Correlation Heatmap  
- 📍 Decision Tree Diagram *(e.g., `plot_tree`)*
- 📍 Confusion Matrix Heatmap

---

## 📎 Tools Used

- Python 3.x
- pandas, numpy
- matplotlib, seaborn
- scikit-learn

---

## ✅ Next Steps

1. Train the **Decision Tree Classifier**
2. Evaluate model using metrics & visualizations
3. Optional: Try Random Forest or SVM for comparison

