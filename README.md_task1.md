
 🧹 Data Cleaning & Preprocessing for Machine Learning

This project demonstrates how to clean and preprocess a raw dataset for use in machine learning models. The steps include handling missing values, encoding categorical data, normalizing features, and visualizing outliers.


 🛠️ Tools & Libraries Used

- **Python** – Programming language
- **Pandas** – Data manipulation and analysis
- **NumPy** – Numerical computations
- **Matplotlib** – Data visualization
- **Seaborn** – Statistical data visualization

---

## 📁 Dataset

This project uses the **Titanic dataset** from Kaggle:  
[https://www.kaggle.com/competitions/titanic/data](https://www.kaggle.com/competitions/titanic/data)



 Steps Performed

1. **Import the Dataset**
   - Load the `.csv` file using `pandas.read_csv()`

2. **Initial Exploration**
   - View shape, data types, and missing values
   - Use `df.info()` and `df.describe()`

3. **Handle Missing Values**
   - Impute using mean, median, or a constant
   - Drop columns or rows if needed

4. **Encoding Categorical Features**
   - Convert text features to numerical using `LabelEncoder` or `pd.get_dummies()`

5. **Normalize or Standardize**
   - Scale numerical features using MinMaxScaler or StandardScaler from `sklearn.preprocessing`

6. **Outlier Detection**
   - Visualize with boxplots using Seaborn
   - Remove or treat outliers as needed

7. **Export Cleaned Data**
   - Save the cleaned DataFrame as `cleaned_data.csv`

 Example Code Snippet
python
import pandas as pd
from sklearn.preprocessing import LabelEncoder, StandardScaler

df = pd.read_csv('titanic.csv')
df['Age'].fillna(df['Age'].median(), inplace=True)
df['Embarked'].fillna(df['Embarked'].mode()[0], inplace=True)

le = LabelEncoder()
df['Sex'] = le.fit_transform(df['Sex'])

scaler = StandardScaler()
df[['Age', 'Fare']] = scaler.fit_transform(df[['Age', 'Fare']])
```

 Output

- A clean, processed dataset ready for machine learning models
- Visualizations showing distributions and outlier detection

