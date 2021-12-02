## Nullcount plot

```python
import matplotlib.pyplot as plt
import pandas as pd

def null_count_barchart(df: pd.DataFrame) -> None:
    null_count = df.isnull().sum(axis=0)
    fig = plt.figure()
    ax = fig.add_axes([0,0,1,1])
    # set Y axis label
    ax.set_ylabel('count')
    # set orientation for X axis labels
    plt.xticks(rotation='vertical')
    plt.axhline(y=len(df))
    # draw bar chart
    ax.bar(null_count.index, null_count)
    plt.show()
```

## Correlation scatter matrix

```python
from itertools import repeat
import matplotlib.pyplot as plt
import math
import pandas as pd
from typing import List, Tuple

def create_scatter_matrix(
        df: pd.DataFrame, 
        n_cols_fig: int,
        columns: List[str], 
        label: str, 
        figsize: Tuple[int, int] = [15, 15]
    ) -> None:
    n_cols = len(columns)
    n_rows = math.ceil(n_cols/n_cols_fig)
    indices = [
        (x, y) for x, z in
        zip(range(n_rows), repeat(range(n_cols_fig)))
        for y in z
    ]
    fig, ax = plt.subplots(nrows=n_rows, ncols=n_cols_fig, figsize=figsize)
    for index, column in enumerate(columns):
        if n_rows == 1 or n_cols_fig == 1:
            if n_rows == 1:
                axis = ax
            else:
                axis = ax[index]
        else:
            row_index, column_index = indices[index]
            axis = ax[row_index, column_index]
        correlation = df[column].corr(df[label])
        axis.set_title(f'{label} vs {column}: corr = {round(correlation, 6)}')
        axis.set_xlabel(f'{column}')
        axis.set_ylabel(f'{label}')
        axis.scatter(
            df[column], df[label],
            marker='o',
            alpha=0.3
        )
```
