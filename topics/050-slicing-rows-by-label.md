title: Slicing Rows By Label
--- |

  While the `.iloc[]` accessor (or slicing rows by location) may feel more intuitive since that resembles the general purpose sequence interface in Python, `.loc[]` accessor (or slicing rows by label) is much more useful in real world.

  Let's first load our dataset:

---
type: live-code
id: 1
code: |
  import pandas as pd

  df = pd.read_csv('assets/data/biopics.csv')
  df.head()
--- |

  As you can see, Pandas has generated default labels for our rows (numbered from 0 onwards). These labels just reflect the location of the rows and will not be very helpful in demonstrating the difference between _slicing by location_ and _slicing by labels_. So, let's set our own index on this `DataFrame` and use the labels from that index to develop an understanding of _slicing by lables_. We'll use `year_release` variable as our index.

---
type: live-code
id: 2
code: |
  df = df.set_index('year_release').sort_index()
  df.head()
--- |

  We can validate that this `DataFrame` is indexed by the `year_release`:

---
type: live-code
id: 3
code: |
  df.index
--- |

  Now, we are ready to explore the `.loc[]` accessor. Let's say, we want to create a slice that contains movies released in year 2014.

---
type: live-code
id: 4
code: |
  df.loc[2014]
--- |

  That was simple, right? Let's say, we want to select the movies released between 2000 to 2013.

---
type: live-code
id: 5
code: |
  df.loc[2000:2013]
--- |

  Note: the label range works slightly differently from location range. In location range, the last value is excluded but in label range, last value is included. So, `df.iloc[2000:2013]` will return rows from location 2000 to 2012 but exclude 2013. `df.loc[2000:2013]` will return rows with label 2000 to 2013.
