# Lyrical Analysis of Blink-182 Songs

## Introduction 
* Analyzing the most common words over all the songs and then creating 6 topics through vector implimentation to group these words under. Then, interpreting an emotional adjective (love song, hate, breakup, etc.) from the compiled result per topic. Next, comparing each song to the emotional adjectives selected to visualize which emotional adjective is closest to the words in the song. Then the songs are sorted by year and the topic of the songs are plotted year vs. number of songs in the year per topic. 

## Setup/Usage
* Here I am practicing my use of processing Natural Language of words on Python 3. 
The packages that are used are: [pandas](https://pandas.pydata.org/pandas-docs/stable/install.html), [nltk](https://www.nltk.org/install.html), [csv](https://docs.python.org/3/library/csv.html), [matplotlib](https://matplotlib.org/3.1.1/users/installing.html) and [sklearn](https://scikit-learn.org/stable/install.html) including [TfidfVectorizer](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html).

## Data
* The Library including this artist's lyric set as well as 380,000+ other artist's lyrics can be found at this [Kaggle Lyrics Dataset](https://www.kaggle.com/gyani95/380000-lyrics-from-metrolyrics).

The open and read CSV file will contain the following fields:

* `index` : Numbered value of song within the entire dataset 
* `song` : song name
* `year` : year the song was released
* `artist` : who wrote the song
* `genre` : genre of song
* `lyrics` : the lyrics contained in the specified song

A search on the Kaggle Lyrics Dataset can confirm if the artist being seeked is available in the dataset before downloading. 

## Process 

* Pandas will read the csv file and save it as a variable to parse through in order to define which artist to select and analyze. We can use artist.head() to view the first 5 songs retrieved. 

![F00B4F4F-0FE3-42FB-9871-2BD0736A8903_4_5005_c](https://user-images.githubusercontent.com/55423732/71784743-d3b26200-2fc4-11ea-9690-eb60343b53e9.jpeg)

* Now to clean up the csv we are reading, set the variable `songs` to include only header fields needed. This inlcudes **song**, **lyrics**, and **year**

![531BA2FE-ED7B-46D0-A3DA-DEEBA84599F4_4_5005_c](https://user-images.githubusercontent.com/55423732/71784892-dca43300-2fc6-11ea-92dc-702322f26e1d.jpeg)

* stopwords are imported from [nltk.corpus](https://www.nltk.org/api/nltk.corpus.html) in order to remove common words from our data set. (Common words that are specific to the selected artist may be added to this list as well)

* [NMF](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.NMF.html) from sklearn will organize the remaining lyrics into common topics and then a for loop is used to return the first 10 words of each topic. 

![A333AE54-2760-499B-9EFD-502A0CB93951_4_5005_c](https://user-images.githubusercontent.com/55423732/71784995-5e489080-2fc8-11ea-9e6d-955ecfa77bcb.jpeg)




Removing common words and selecting a theme per top words used in songs of that year 
Setting value of 'important' words to either 0 or 1 and taking the sum of 'important' words per song per year
Plot 'important' words vs Year to see the artists 'feelings' throughout their career on the data base
