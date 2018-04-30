title: Single Column As Series
--- |

  There are times when we want to retrieve one of the `DataFrame` columns as a `Series`. Part of the reason would be that there are some methods supported by `Series` but not supported by a `DataFrame`.

  Let's first load our dataset:

---
type: live-code
id: 1
code: |
  import pandas as pd

  df = pd.read_csv('assets/data/biopics.csv')
  df.head()
--- |

  Let's say, we want to get `year_release` column as a Pandas `Series`, we can use a variation of the columnar slicing syntax to get the `Series`:

---
type: live-code
id: 2
code: |
  s = df['year_release']
  s.head()
--- |

  We must be careful about the syntax here. When we provide an array of column names as index, we get a `DataFrame` back:

---
type: live-code
id: 3
code: |
  type( df[ ['year_release'] ] )
--- |

  However, when we provide a single column name as index, we get a `Series` back:

---
type: live-code
id: 4
code: |
  type( df['year_release'] )
--- |

  Why get a `Series`? Why not just always work with a `DataFrame`? That's because a `Series` object supports operations that a `DataFrame` does not. Here is one such operation:

---
type: live-code
id: 5
code: |
  df['year_release'].value_counts()
