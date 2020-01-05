# Lyrical Analysis of Blink-182 Songs

## Setup/Usage
* Here I am practicing my use of processing Natural Language of words on Python 3. 
The packages that are used are: [pandas](https://pandas.pydata.org/pandas-docs/stable/install.html), [nltk](https://www.nltk.org/install.html), [csv](https://docs.python.org/3/library/csv.html), [matplotlib](https://matplotlib.org/3.1.1/users/installing.html) and [sklearn](https://scikit-learn.org/stable/install.html) including [TfidfVectorizer](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html).

## Data
* The Library including this artist's lyric set as well as 380,000+ other artist's lyrics can be found at this [Kaggle Lyrics Dataset](https://www.kaggle.com/gyani95/380000-lyrics-from-metrolyrics).

The open and read CSV file will contain the following fields:

* |"index"| : Numbered value of song within the entire dataset 



Importing lyrics from a csv file, organizing the data into defined artist's songs through the years (selected Blink182 from lyric CSV file)


Removing common words and selecting a theme per top words used in songs of that year 
Setting value of 'important' words to either 0 or 1 and taking the sum of 'important' words per song per year
Plot 'important' words vs Year to see the artists 'feelings' throughout their career on the data base
