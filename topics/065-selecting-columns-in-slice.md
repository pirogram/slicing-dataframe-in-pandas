title: Selecting Columns in a Slice
--- |

  So far, we looked at multiple ways to slice a `DataFrame`. All of those perform either vertical slicing (or column based slicing) or horizontal slicing (or row based slicing). The column based slicing works directly on the `DataFrame` (e.g. `df[ ['col1', 'col2'] ]`). The row based slicing works either via the `.iloc[]` accessor (integer position based) or the `.loc[]` accessor (label or boolean vector based). We'll now look at slicing a `DataFrame` in such a way that we can be selective about rows as well as columns that we want in our slice.

  We looked at following syntax of `.loc[]` accessor so far:

  ```
  df.loc[rows i want]
  ```

  The full syntax of `.loc[]` accessor is:

  ```
  df.loc[rows i want, columns i want]
  ```

  Let's look at some examples. First, we need to load the dataset:

---
type: live-code
id: 1
code: |
  import pandas as pd
  df = pd.read_csv('assets/data/biopics.csv')
  df.head()
--- |

  As we saw earlier, the following code gives us all the rows where `year_release` is `2014`:

---
type: live-code
id: 2
code: |
  df.loc[ df['year_release'] == 2014 ]
--- |

  What if we want to select only `country` and `director` columns from the `DataFrame` as part of this slice? We can use the full syntax of `.loc[]` (i.e. `df.loc[rows i want, columns i want]`):

---
type: live-code
id: 3
code: |
  df.loc[ df['year_release'] == 2014, ['country', 'director'] ]
