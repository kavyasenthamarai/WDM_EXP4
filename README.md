### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 
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
```python
import pandas as pd
import matplotlib.pyplot as plt



visitor_df = pd.read_csv('/content/clustervisitor.csv')


age_groups = {
    'Young': (visitor_df['Age'] <= 30),
    'Middle-aged': ((visitor_df['Age'] > 30) & (visitor_df['Age'] <= 50)),
    'Elderly': (visitor_df['Age'] > 50)
}


visitor_counts = [sum(condition) for condition in age_groups.values()]
age_group_labels = list(age_groups.keys())

plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()


for group, condition in age_groups.items():
    visitors_in_group = visitor_df[condition]
    print(f"Visitors in {group} age group:")
    print(visitors_in_group)

print("Visitor segmentation based on age groups complete.")

```
### Output:
![image](https://github.com/kavyasenthamarai/WDM_EXP4/assets/118668727/84dee15d-86de-4605-a370-2cfe2f48bae8)

![image](https://github.com/kavyasenthamarai/WDM_EXP4/assets/118668727/e33c15bd-b30c-40ca-8d62-97b05cd957bc)

### Result:
Visitor segmentation based on age groups successfully completed.
