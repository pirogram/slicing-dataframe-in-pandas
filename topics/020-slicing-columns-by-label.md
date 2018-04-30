title: Slicing Columns By Label
--- |

  For any given dataset, we may not be interested in all the variables. In such cases, we may want to create a `DataFrame` that has only those variables that we want to deal with. This is when we use the columnar slicing approach.

  Let's first load our dataset:

---
type: live-code
id: 1
code: |
  import pandas as pd

  df = pd.read_csv('assets/data/biopics.csv')
  df.head()
--- |

  Let's say, we are interested in only three variables for now: `country`, `year_release` and `box_office`. Here is how we could create a slice of the `DataFrame` by selecting the columns that we want.

---
type: live-code
id: 2
code: |
  df_slice = df[ ['country', 'year_release', 'box_office'] ]
  df_slice.head()
--- |

  As you can notice, we can index a `DataFrame` as if it was a list and we can pass an array of column labels (aka names) that we wish to keep in our slice.

  The original `DataFrame` continues to have all the columns intact:

---
type: live-code
id: 3
code: |
  df.head()
--- |

  We could also create a slice with just one column in it. While it may seem unnecessary but for the purpose of illustration, here is an example slice with just `year_release` column.

---
type: live-code
id: 4
code: |
  df_slice = df[ ['year_release'] ]
  df_slice.head()
---
