title: Exercises 2
--- |

  For the purpose of these exercises, we'll use the dataset related to [Characters in DC Comics](assets/data/dc-wikia-data.csv). This data is sourced from [fivethirtyeight](https://github.com/fivethirtyeight/data/tree/master/comic-characters).

  Here are the variables in this dataset:

  Variable | Definition
  ---|---------
  `page_id` | The unique identifier for that characters page within the wikia
  `name` | The name of the character
  `urlslug` | The unique url within the wikia that takes you to the character
  `ID` | The identity status of the character (Secret Identity, Public identity, [on marvel only: No Dual Identity])
  `ALIGN` | If the character is Good, Bad or Neutral
  `EYE` | Eye color of the character
  `HAIR` | Hair color of the character
  `SEX` | Sex of the character (e.g. Male, Female, etc.)
  `GSM` | If the character is a gender or sexual minority (e.g. Homosexual characters, bisexual characters)
  `ALIVE` | If the character is alive or deceased
  `APPEARANCES` | The number of appearances of the character in comic books (as of Sep. 2, 2014. Number will become increasingly out of date as time goes on.)
  `FIRST APPEARANCE` | The month and year of the character's first appearance in a comic book, if available
  `YEAR` | The year of the character's first appearance in a comic book, if available

  Let's first load the dataset:

---
type: live-code
id: 1
code: |
  import pandas as pd

  df = pd.read_csv('assets/data/dc-wikia-data.csv')
  df.head()

---
type: fill-in-the-blank-question
id: 2
question: |
  Create a `DataFrame` slice where `ID` variable has value `Secret Identity`. How many rows are there in the slice? (Note: you can use the `.shape` attribute to find out the number of rows in a `DataFrame`).

code: |
  # Slice the `df` and look at its `.shape`

blanks:
  - label: Number of rows
    answer: 2408

solution: |
  df[ df['ID'] == 'Secret Identity' ].shape[0]

---
type: fill-in-the-blank-question
id: 3
question: |
  How many "Blue Eyed", "Male Characters" are there that align with "Good Characters"? To find out, create a slice where `EYE` is `Blue Eyes`, `SEX` is `Male Characters` and `ALIGN` is `Good Characters`.

code: |
  # Slice the `df` and look at its `.shape`

blanks:
  - label: Count of Characters
    answer: 334

solution: |
  df[ (df['ALIGN'] == 'Good Characters') & (df['EYE'] == 'Blue Eyes') & (df['SEX'] == 'Male Characters') ].shape[0]
  
---
type: fill-in-the-blank-question
id: 4
question: |
  How many `Female Characters` that first appeared after the year `1950` are still alive? For this, you should slice on `SEX`, `ALIVE` and `YEAR` variables.

code: |
  # Slice the `df` and look at its `.shape`.

blanks:
  - label: Count of Characters
    answer: 1519

solution: |
  df[ (df['YEAR'] > 1950) & (df['ALIVE'] == 'Living Characters') & (df['SEX'] == 'Female Characters') ].shape[0]

---
type: fill-in-the-blank-question
id: 5
question: |
  Among the first 1000 records in this dataset, how many `Female Characters` that first appeared after the year `1950` are _not_ alive? For this, you should first create a slice of initial 1000 rows. You can then further slice it on `SEX`, `ALIVE` and `YEAR` variables.

code: |
  # Slice the `df` and look at its `.shape`.

blanks:
  - label: Count of Characters
    answer: 60

solution: |
  df_first_1000 = df.iloc[:1000]

  df_first_1000[ (df_first_1000['YEAR'] > 1950) & (df_first_1000['ALIVE'] == 'Living Characters') & (df_first_1000['SEX'] == 'Female Characters') ].shape[0]

---
type: coding-question
id: 6
question: |
  Fix the following code so that the slice `df_slice` contains columns `name`, `EYE` and `HAIR`.

code: |
  df_slice = df[ ['name', 'EYE', 'ALIVE'] ]

tests: |
  assert list(df_slice.columns) == ['name', 'EYE', 'HAIR']

solution: |
  df_slice = df[ ['name', 'EYE', 'HAIR'] ]

---
type: coding-question
id: 7
question: |
  Complete the following code so that the slice `df_slice` contains columns `ALIVE` and `ALIGN`.

code: |
  df_slice =

tests: |
  assert list(df_slice.columns) == ['ALIVE', 'ALIGN']

solution: |
  df_slice = df[ ['ALIVE', 'ALIGN'] ]

---
type: coding-question
id: 8
question: |
  Complete the following code so that the slice `df_slice` contains columns `ALIVE` and `ALIGN` and only those rows where `YEAR` is 1950 or more.

code: |
  df_slice =

tests: |
  assert list(df_slice.columns) == ['ALIVE', 'ALIGN']
  assert df_slice.shape[0] == 6517  # number of rows in slice

solution: |
  df_slice = df.loc[ df['YEAR'] >= 1950, ['ALIVE', 'ALIGN'] ]
