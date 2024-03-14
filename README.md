### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 14/03/2024
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```
NAME:SITHI HAJARA I
REG NO:212221230102
```
```python

# Importing required libraries

import pandas as pd
import matplotlib.pyplot as plt

# read the data
visitors_df = pd.read_csv("clustervisitor.csv") 

# Define age groups
age_groups = {
    'Young': (visitors_df['Age'] <= 30),
    'Middle-aged': ((visitors_df['Age'] > 30) & (visitors_df['Age'] <= 50)),
    'Elderly': (visitors_df['Age'] > 50)
}

# Print visitors in each age group
for group, condition in age_groups.items():
    visitors_in_group = visitors_df[condition]
    print(f"Visitors in {group} age group:")
    print(visitors_in_group)
    print()

# Count visitors in each age group
visitors_counts = []
for group, condition in age_groups.items():
    visitors_in_group = visitors_df[condition]
    visitors_counts.append(len(visitors_in_group))

# Plot the distribution of visitors across age groups
age_group_labels = list(age_groups.keys())
plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitors_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()

```
### Output:

![image](https://github.com/sithihajara/WDM_EXP4/assets/94219582/782e8640-8d81-4ac0-a707-cc3ca63f03da)

![image-1](https://github.com/sithihajara/WDM_EXP4/assets/94219582/bb637368-7a2c-419f-a74d-e58dd47eafc8)



### Result:
Thus,the Cluster and Visitor Segmentation for Navigation patterns in Python implemented successfully.

