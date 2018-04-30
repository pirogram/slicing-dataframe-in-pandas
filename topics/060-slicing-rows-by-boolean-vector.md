title: Slicing Rows By Boolean Vector
--- |

  A `DataFrame` can be sliced using a boolean vector. Even though this method has come up at the end of our discussion on slicing, it is probably the most useful method to slice a `DataFrame` by rows.

  As usual, let's first load our dataset:

---
type: live-code
id: 1
code: |
  import pandas as pd

  df = pd.read_csv('assets/data/biopics.csv')
  df.head()
--- |

  Let's say, we want to create a slice with movies that were released in year 2014, here is how we can go about it:

---
type: live-code
id: 2
code: |
  df.loc[ df['year_release'] == 2014 ]
--- |

  If you recall the vectorized operations from [`ndarray`](/topic/ndarray), this is very similar to slicing an `ndarray` with a boolean vector.

  We can also apply multiple conditions in our slice. Let's say, we want to restrict our slice to movies released in 2014 in US.

---
type: live-code
id: 3
code: |
  df.loc[ (df['year_release'] == 2014) & (df['country'] == 'US') ]
