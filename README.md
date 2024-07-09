Student Performance Analysis
This repository contains a Jupyter Notebook that analyzes student performance data from a CSV file. The analysis includes data cleaning, exploratory data analysis, and visualization to understand various factors affecting student performance.

Getting Started
Prerequisites
Make sure you have the following libraries installed:

pandas
seaborn
numpy
matplotlib
You can install these libraries using pip:

bash
Copy code
pip install pandas seaborn numpy matplotlib
Data
The dataset used in this analysis is Student_data.csv, which contains the following columns:

StudentID
Age
Gender
Ethnicity
ParentalEducation
StudyTimeWeekly
Absences
Tutoring
ParentalSupport
Extracurricular
Sports
Music
Volunteering
GPA
GradeClass
Running the Notebook
Clone this repository:
bash
Copy code
git clone <repository-url>
Navigate to the directory:
bash
Copy code
cd <repository-directory>
Open the Jupyter Notebook:
bash
Copy code
jupyter notebook Student_Performance_Analysis.ipynb
Analysis Overview
Data Cleaning
The dataset is read using pandas.
The first few rows of the dataset are displayed using df.head().
The last few rows of the dataset are displayed using df.tail().
The dataset's structure and summary statistics are examined using df.info() and df.describe().
Exploratory Data Analysis (EDA)
Gender Distribution: The gender distribution of students is visualized using a count plot.
Numerical Data Distribution: Histograms are created for numerical columns like Absences, Tutoring, ParentalSupport, Extracurricular, Sports, and GPA.
Categorical Data Distribution: Count plots are created for categorical columns like Tutoring, ParentalSupport, Extracurricular, Sports, Music, and Volunteering.
Correlation Analysis: A correlation matrix is computed and visualized using a heatmap to understand the relationships between different variables.
Pair Plot: Pair plots are created to visualize the relationships between numerical variables.
Visualizations
Count Plot for Gender Distribution:
python
Copy code
plt.figure(figsize=(5,5))
sns.countplot(data=df, x="Gender")
plt.show()
Histograms for Numerical Columns:
python
Copy code
numerical_columns = ['Absences', 'Tutoring', 'ParentalSupport', 'Extracurricular', 'Sports', 'GPA']
for col in numerical_columns:
    plt.figure()
    sns.histplot(df[col], bins=20, kde=True)
    plt.title(f'Distribution of {col}')
    plt.show()
Count Plots for Categorical Columns:
python
Copy code
categorical_columns = ['Tutoring', 'ParentalSupport', 'Extracurricular', 'Sports', 'Music', 'Volunteering']
for col in categorical_columns:
    plt.figure()
    sns.countplot(x=df[col])
    plt.title(f'Distribution of {col}')
    plt.show()
Pair Plot:
python
Copy code
sns.pairplot(df[numerical_columns])
plt.suptitle('Pair Plot of Numerical Variables', y=1.02)
plt.show()
Correlation Matrix Heatmap:
python
Copy code
correlation_matrix = df.corr()
plt.figure(figsize=(10, 8))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.title('Correlation Matrix')
plt.show()
Conclusion
This analysis provides insights into various factors affecting student performance. By understanding these factors, educators and policymakers can develop strategies to improve educational outcomes.

