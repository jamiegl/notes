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
