codealpha# DATA-VISUALIZATION

import matplotlib.pyplot as plt
import seaborn as sns

# Set style for plots
sns.set_style('whitegrid')

content_type_counts = df['type'].value_counts()

plt.figure(figsize=(8, 8))
plt.pie(content_type_counts, labels=content_type_counts.index, autopct='%1.1f%%', startangle=90, colors=['#FF6347', '#4682B4'])
plt.title('Distribution of Content Types on Netflix')
plt.show()

plt.figure(figsize=(12, 6))
sns.countplot(data=df, x='rating', hue='rating', order=df['rating'].value_counts().index, palette='viridis', legend=False)
plt.title('Distribution of Content Ratings on Netflix')
plt.xlabel('Rating')
plt.ylabel('Number of Titles')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

plt.figure(figsize=(12, 6))
sns.histplot(data=df, x='release_year', bins=30, kde=True, color='skyblue')
plt.title('Distribution of Content Release Years on Netflix')
plt.xlabel('Release Year')
plt.ylabel('Number of Titles')
plt.tight_layout()
plt.show()

