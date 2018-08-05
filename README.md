# xlsx-metadata
Really lightweight lib for peeking into xlsx column/row size before you try to open the file with something else

```python
from metadata import get_dimensions

dimensions = get_dimensions('/path/to/my/real_big_workbook.xlsx', 'sheet1')
print(dimensions['end_column'])

>>> 16834

print(dimensions['end_row'])

>>> 1200000
```

This information is stored as metadata in the first few bytes of `.xlsx` files. For some reason no other libraries (xlrd, openpyxl) seem to give the users access to this data directly.
