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
