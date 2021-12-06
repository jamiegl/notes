## Column Cleaner



```python
import re
from typing import List

def column_cleaner(columns: List[str], mode: str = 'Title Case'):
    def snakeify(column: str, mode: str):
        trimmed_col = column.strip()
        if mode == 'Title Case':
            return re.sub('(.*?)[\-\s,]+(.*?)', r'\1_\2', trimmed_col).lower()
        elif mode == 'camelCase':
            return re.sub(r'(?<!^)(?=[A-Z])', '_', trimmed_col).lower()
    return [snakeify(x, mode) for x in columns]a
```

## Lambda aggregates

Example where we get the nullcount and total number of rows from a table grouped over country and schooling (where schooling is a linear scale of 1-10):

```python
le_data[['Country', 'Schooling']].groupby(
    'Country'
).agg([lambda x: x.isnull().sum(), lambda x: len(x)])
```

## Unpivot/melt

`id_vars` will remain unchanged and the `value_vars` will be pivoted on.

```python
upvt_dh_cat_df = pd.melt(
    dh_cat_df,
    id_vars=['Year', 'Month'],
    value_vars=[
        x for x in dh_cat_df.columns if x not in [
            'Date', 'Year', 'Month'
        ]
    ]
)
```
