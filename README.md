# Some useful tools and redirection to examples

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

- add more ticks on x/y axis 
https://github.com/danielliu99/DS_toolbox/blob/main/DS_takehome_challenges/03Retention.ipynb 
```python
ht = sns.histplot(data=ret_quit, x='stay_days', 
             bins=50)
ht.set_xticks(range(100,1800,100))
```
