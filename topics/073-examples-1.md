title: Examples 1
--- |

  For the purpose of this discussion, let's look at a dataset related to [births in US](assets/data/US_births_2000-2014_SSA.csv). This data is sourced from [fivethirtyeight](https://github.com/fivethirtyeight/data/tree/master/births). Feel free to download this dataset and play with it in your own Jupyter Notebook.

  This is what the dataset looks like:

  year|month|date_of_month|day_of_week|births
  -|-|-|-|-
  2000|1|1|6|9083
  2000|1|2|7|8006
  2000|1|3|1|11363
  2000|1|4|2|13032
  2000|1|5|3|12558
  2000|1|6|4|12466
  2000|1|7|5|12516
  2000|1|8|6|8934

---
type: live-code
id: 1
code: |
  import pandas as pd

  df = pd.read_csv('assets/data/US_births_2000-2014_SSA.csv')
  df.head()
--- |

  ## `year` is 2000

  Let's look at two ways to create this slice: boolean vectors and row labels.

---
type: live-code
id: 2
code: |
  # boolean vector
  df.loc[ df['year'] == 2000 ]

---
type: live-code
id: 3
code: |
  # create an index on year
  df_indexed = df.set_index('year')

  # slice
  df_indexed.loc[2000]

--- |

  ## `year` between 2001 to 2010 and the `births` are more than 5000

  We'll use the boolean vector method for this slice since that method gives us the maximum flexibility.

---
type: live-code
id: 4 
code: |
  df.loc[ (df['year'] >= 2001) & (df['year'] <= 2010) & (df['births'] > 5000) ]
--- |

  ## `day_of_week` and `births` columns

  Let's say, we want to work with only two columns: `day_of_week` and `births`. Here is how we can create the slice:

---
type: live-code
id: 5
code: |
  df[ ['day_of_week', 'births'] ]
--- |

  ## First 5 Rows

  If we want to extract first 5 rows, we can use the `.iloc[]` accessor.

---
type: live-code
id: 6
code: |
  df.iloc[:5]
