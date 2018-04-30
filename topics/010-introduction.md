title: Introduction
--- |

    `DataFrame` is the core data structure in Pandas. Usually, for any exploratory data analysis work, we would first load the dataset in a `DataFrame` and then go from there.

    Slicing is an important aspect of working with a `DataFrame`. It lets us select specific sections of the `DataFrame` either horizontally or vertically (or  both).

    In this topic, we'll look at the overall slicing syntax and perform some common slicing operations.

    For illustration purposes, we'll use a dataset that contains information about biographical movies. The data was sourced from [fivethirtyeight](https://github.com/fivethirtyeight/data/tree/master/biopics) and has the following variables:

    Variable | Definition
    ---|---------
    `title` | Title of the film.
    `site` | URL from IMDB.
    `country` | Country of origin.
    `year_released` | Year of release.
    `box_office` | Gross earnings at U.S. box office.
    `director` | Director of film.
    `number_of_subjects` | The number of subjects featured in the film.
    `subject` | The actual name of the featured subject.
    `type_of_subject` | The occupation of subject or reason for recognition.
    `race_known` | Indicates whether the subject’s race was discernible based on background of self, parent, or grandparent.
    `subject_race` | Race of the subject.
    `person_of_color` | Dummy variable that indicates person of color.
    `subject_sex` | Sex of subject.
    `lead_actor_actress` | The actor or actress who played the subject.

    Here is a sample from the dataset:

    title|site|country|year_release|box_office|director|number_of_subjects|subject|type_of_subject|race_known|subject_race|person_of_color|subject_sex|lead_actor_actress
    -|-|-|-|-|-|-|-|-|-|-|-|-|-|
    10 Rillington Place|http://www.imdb.com/title/tt0066730/|UK|1971|-|Richard Fleischer|1|John Christie|Criminal|Unknown||0|Male|Richard Attenborough
    12 Years a Slave|http://www.imdb.com/title/tt2024544/|US/UK|2013|$56.7M|Steve McQueen|1| Solomon Northup|Other|Known|African American|1|Male|Chiwetel Ejiofor
    127 Hours|http://www.imdb.com/title/tt1542344/|US/UK|2010|$18.3M|Danny Boyle|1|Aron Ralston|Athlete|Unknown||0|Male|James Franco
    1987|http://www.imdb.com/title/tt2833074/|Canada|2014|-|Ricardo Trogi|1|Ricardo Trogi|Other|Known|White|0|Male|Jean-Carl Boucher
    20 Dates|http://www.imdb.com/title/tt0138987/|US|1998|$537K|Myles Berkowitz|1|Myles Berkowitz|Other|Unknown||0|Male|Myles Berkowitz
    21|http://www.imdb.com/title/tt0478087/|US|2008|$81.2M|Robert Luketic|1|Jeff Ma|Other|Known|Asian American|1|Male|Jim Sturgess
    24 Hour Party People|http://www.imdb.com/title/tt0274309/|UK|2002|$1.13M|Michael Winterbottom|1|Tony Wilson|Musician|Known|White|0|Male|Steve Coogan
    42|http://www.imdb.com/title/tt0453562/|US|2013|$95M| Brian Helgeland|1|Jackie Robinson|Athlete|Known|African American|1|Male|Chadwick

    Before we proceed, it would be better for you to look at the data and develop some perspective about it.

    We'll look at multiple ways of slicing a `DataFrame`:
    * Slicing Columns by Label
    * Slicing Rows by Location
    * Slicing Rows by Label
    * Slicing Rows by Boolean Vector
