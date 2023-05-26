# Pythoncode
Ajay kumar jha  write a program to histogram in python version


import seaborn as sns
import matplotlib.pyplot as plt

# Import seaborn and load the Iris dataset
sns.set()
iris = sns.load_dataset("iris")

# Calculate mean, median, maximum, and minimum values for each column feature
column_features = iris.columns[:-1]
statistics = iris.describe().loc[['mean', '50%', 'max', 'min'], column_features]
print("Statistics for each column feature:")
print(statistics)

# Plot a histogram using one of the numeric features (e.g., sepal_length)
sns.histplot(data=iris, x="sepal_length", kde=True)
plt.title("Histogram of Sepal Length")
plt.show()

# Plot an empirical cumulative distribution function (ECDF) plot
sns.ecdfplot(data=iris, x="sepal_length")
plt.title("ECDF Plot of Sepal Length")
plt.xlabel("Sepal Length")
plt.ylabel("Cumulative Probability")
plt.show()

# Use pairplot to visualize the correlation among the features
sns.pairplot(data=iris)
plt.title("Pairplot of Iris Dataset")
plt.show()
