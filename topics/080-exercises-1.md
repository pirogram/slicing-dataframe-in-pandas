title: Excercises 1
---

type: multiple-choice-question
id: 1
question: |
  What would the following code yield?

  ```
  df.loc[4:10]
  ```
options:
  - text: a `DataFrame` slice from 4th row to 10th row.
  - text: a `DataFrame` slice from 4th row to 9th row.
  - text: a `DataFrame` slice from label number 4 to label number 10.
    correct: true
  - text: a `DataFrame` slice from label number 4 to label number 9.

---
type: multiple-choice-question
id: 2
question: |
  What would the following code yield?

  ```
  df.loc[ ['Luke', 'Leila', 'Anakin'] ]
  ```
options:
  - text: a `DataFrame` slice made from rows that are labeled `Luke`, `Leila` or `Anakin`.
    correct: true
  - text: This is invalid syntax because `iloc[]` slices by row location and not row labels.
  - text: This is invalid syntax because we can slice by row labels only when the labels are integers.

---
type: multiple-choice-question
id: 3
question: |
  What would the following code yield?

  ```
  df.iloc[4:10]
  ```
options:
  - text: a `DataFrame` slice from 4th row to 10th row.
  - text: a `DataFrame` slice from 4th row to 9th row.
    correct: true
  - text: a `DataFrame` slice from label number 4 to label number 10.
  - text: a `DataFrame` slice from label number 4 to label number 9.

---
type: multiple-choice-question
id: 4
question: |
  What would the following code yield?

  ```
  df.iloc[ ['Luke', 'Leila', 'Anakin'] ]
  ```
options:
  - text: a `DataFrame` slice made from rows that are labeled `Luke`, `Leila` or `Anakin`.
  - text: This is invalid syntax because `iloc[]` slices by row location and not row labels.
    correct: true
  - text: This is invalid syntax because we can slice by row labels only when the labels are integers.

---
type: multiple-choice-question
id: 5
question: |
  What would the following code yield?

  ```
  df['max']
  ```
options:
  - text: a `DataFrame` slice made from column named `max`.
  - text: a `Series` containing the values of column named `max`.
    correct: true
  - text: A `DataFrame` slice made from rows labeled `max`.

---
type: multiple-choice-question
id: 6
question: |
  What would the following code yield?

  ```
  df[ ['max', 'min'] ]
  ```
options:
  - text: a `DataFrame` slice made from columns `max` and `min`.
    correct: true
  - text: a `DataFrame` slice made from rows labeled as `max` and `min`.

---
type: multiple-choice-question
id: 7
question: |
  What would the following code yield?

  ```
  df.loc[ df['actor'] == 'Tom Hanks', ['director', 'movie_name'] ]
  ```
options:
  - text: a `DataFrame` slice made from rows where the column `actor` has value `Tom Hanks` and all columns.
  - text: a `DataFrame` slice made from rows where the column `actor` has value `Tom Hanks` and only two columns - `director` & `movie_name`.
    correct: true
  - text: a `DataFrame` slice made from rows where the row label `actor` has value `Tom Hanks` and only two columns - `director` & `movie_name`.