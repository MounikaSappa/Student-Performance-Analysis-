# Student-Performance-Analysis-
This project analyzes student performance data to identify trends and insights based on gender, study time, and parental education. It uses Python (Pandas, Matplotlib) to clean and visualize the data.



## Tools Used
- Python
- Pandas
- Matplotlib

## Key Insights
- Female students tend to score higher on average in reading and writing.
- More study time generally leads to better math scores.


import pandas as pd
import matplotlib.pyplot as plt

# Load the data
df = pd.read_csv('student_data.csv')

# Display basic info
print(df.head())

# Average scores by gender
gender_avg = df.groupby('gender')[['math_score', 'reading_score', 'writing_score']].mean()
print("\nAverage Scores by Gender:\n", gender_avg)

# Study time vs math score
plt.figure(figsize=(8, 5))
df.groupby('study_time')['math_score'].mean().plot(kind='bar', color='skyblue')
plt.title("Average Math Score by Study Time")
plt.ylabel("Math Score")
plt.xlabel("Study Time")
plt.tight_layout()
plt.show()

pandas
matplotlib
