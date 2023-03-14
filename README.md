# Some useful tools and examples

## Visualization 

### Plots
- `sns.relplot()`  
https://github.com/danielliu99/DS_toolbox/blob/main/DS_takehome_challenges/03Retention.ipynb 
```python
sns.relplot(data=tab1, x='day', y='employee_headcount', 
            kind='line', 
            hue='company_id', 
            height=8, aspect=1.5, 
            lw=1).set(title='Accumulated Headcount')
```

### Style control

- Global figure size 
```python
sns.set(rc={'figure.figsize':(15,6)})
```

- Add more ticks on x/y axis 
https://github.com/danielliu99/DS_toolbox/blob/main/DS_takehome_challenges/03Retention.ipynb 
```python
ht = sns.histplot(data=ret_quit, x='stay_days', 
             bins=50)
ht.set_xticks(range(100,1800,100))
```

- Rotate x axis label 
https://github.com/danielliu99/DS_toolbox/blob/main/DS_takehome_challenges/03Retention.ipynb
```python
cp = sns.catplot(data=tmp2, x='bin_salary', y='stay_days', 
                 kind='point', 
                 alpha=0.4,
                 height=8, aspect=1.5)
cp.fig.suptitle('Days stay in the company as per different salary')
cp.set_xticklabels(rotation=30)
```


## Preprocessing 

### Datetime 
- read data 
```python 
pd.read_csv('...', parse_dates=[['join_date', 'quit_date']])
```
- Create a time series 
```python
pd.date_range(start='2011-01-24', 
                          end='2015-12-10', 
                          freq='D')
```

- Resample 
```python
tab1_month.groupby(by=[pd.Grouper(freq='M'), 'company_id']).max()
```

- Offset
```python
sub_retention['join_date'] + pd.DateOffset(days=365))
```


## Modelling

### Decision Tree 

- plot feature importance 
https://github.com/danielliu99/DS_toolbox/blob/main/DS_takehome_challenges/03Retention.ipynb 
```python
ft_imp = pd.DataFrame(clf.feature_importances_, index=X.columns, columns=['Importance']).sort_values('Importance', ascending=False)
bp = sns.barplot(data=ft_imp, x='Importance', y=ft_imp.index)
bp.set_title('Feature Importance')
bp.bar_label(bp.containers[0])
```

- plot the tree 
```python
import graphviz
from sklearn import tree
dot_data = tree.export_graphviz(clf, out_file=None, feature_names=X.columns, class_names=['Stay Longer', 'Quit in 1 year'], 
                                filled=True, rounded=True, special_characters=True)  
graph = graphviz.Source(dot_data)
graph
``` 


