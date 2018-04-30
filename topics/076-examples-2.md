title: Examples 2
--- |

  For the purpose of this discussion, let's look at a dataset related to [college majors](assets/data/college-majors.csv). This data is sourced from [fivethirtyeight](https://github.com/fivethirtyeight/data/tree/master/college-majors). Feel free to download this dataset and play with it in your own Jupyter Notebook.

  This is what the dataset looks like:

  | Major_code|Major|Major_category|Total|Employed|Employed_full_time_year_round|Unemployed |
  | - | - | - | - | - | - | - |
  | 1100|GENERAL AGRICULTURE|Agriculture & Natural Resources|128148|90245|74078|2423 |
  | 1101|AGRICULTURE PRODUCTION AND MANAGEMENT|Agriculture & Natural Resources|95326|76865|64240|2266 |
  | 1102|AGRICULTURAL ECONOMICS|Agriculture & Natural Resources|33955|26321|22810|821 |
  | 1103|ANIMAL SCIENCES|Agriculture & Natural Resources|103549|81177|64937|3619 |
  | 1104|FOOD SCIENCE|Agriculture & Natural Resources|24280|17281|12722|894 |
  | 1105|PLANT SCIENCE AND AGRONOMY|Agriculture & Natural Resources|79409|63043|51077|2070 |
  | 1106|SOIL SCIENCE|Agriculture & Natural Resources|6586|4926|4042|264 |
  | 1199|MISCELLANEOUS AGRICULTURE|Agriculture & Natural Resources|8549|6392|5074|261 |
  | 1301|ENVIRONMENTAL SCIENCE|Biology & Life Science|106106|87602|65238|4736 |
  | 1302|FORESTRY|Agriculture & Natural Resources|69447|48228|39613|2144 |

---
type: live-code
id: 1
code: |
  import pandas as pd

  df = pd.read_csv('assets/data/college-majors.csv')
  df.head()
--- |

  Please take a moment to [develop a perspective](/topic/perspective-on-data-in-data-analysis) about this dataset. This will aid in understanding rest of the material in this section.

  ## `Major_category` as `Business`

  Let's say, we want to select all rows where `Major_category` is `Business`. There are two ways to do it:

---
type: live-code
id: 2
code: |
  # Slice by boolean vector
  df.loc[ df['Major_category'] == 'Business' ]

---
type: live-code
id: 3
code: |
  # Slice by row labels
  df_indexed = df.set_index('Major_category')
  df_indexed.loc['Business']
--- |

  ## First 10 Rows

  If we want to select rows by their location, we can use the `.iloc[]` accessor. Here is how we can fetch the first 10 rows from the `DataFrame`:

---
type: live-code
id: 4
code: |
  df.iloc[0:10]
--- |

  ## `Major_category` as `Engineering` or `Business` AND `Employed` more than 10000

  Let's say, we want to extract the rows where `Major_category` is either `Engineering` or `Business` and the `Employed` number is more than 10000. Here is how we could go about it:

---
type: live-code
id: 5
code: |
  df[ ((df['Major_category'] == 'Engineering') | (df['Major_category'] == 'Business')) & (df['Employed'] > 10000) ]
--- |

  ## Select `Major_category` and `Unemployed` columns

  Let's say, we want to deal with only two columns: `Major_category` and `Unemployed`. Here is how we can slice the `DataFrame` for the same:

---
type: live-code
id: 6
code: |
  df[ ['Major_category', 'Unemployed'] ]
