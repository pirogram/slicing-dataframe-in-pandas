title: Slicing Rows By Location
--- |

  In this section, we'll look at slicing a `DataFrame` horizontally (i.e. select a few rows). In this section, we'll look at slicing by row location.

  Let's first load our dataset:

---
type: live-code
id: 1
code: |
  import pandas as pd

  df = pd.read_csv('assets/data/biopics.csv')
  df.head()
--- |

  In a `DataFrame`, first row location is `0`, second row location is `1`, third row location is `2`, so on so forth. So, if we want to create a slice with first 10 rows, we'll use the [`iloc[]`](http://pandas.pydata.org/pandas-docs/version/0.22.0/generated/pandas.DataFrame.iloc.html) accessor on our `DataFrame`. Here is what the code looks like:

---
type: live-code
id: 2
code: |
  # first 10 rows
  df.iloc[:10]
---

type: live-code
id: 3
code: |
  # Row locations 1, 3 and 4
  df.iloc[ [1, 3, 4] ]
--- |

  `iloc` stands for _integer location_. It models the `DataFrame` as a list of rows.

  There is a small caveat in creating a slice of a single row. `df.iloc[1]` will return a `Series` instead of a `DataFrame`. Example:

---
type: live-code
id: 4
code: |
  # Retrieving a single row returns a Series and not a DataFrame slice.
  df.iloc[1]
--- |

  If we want a single row as a `DataFrame` instead of a `Series`, we need to specify a range:

---
type: live-code
id: 5
code: |
  # Retrieve row location 1 as a DataFrame
  df.iloc[1:2]