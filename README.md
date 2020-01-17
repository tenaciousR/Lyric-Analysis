# Lyrical Analysis of Blink-182 Songs

## Introduction 
* Analyzing the most common words over all the songs and then creating 6 topics through vector implimentation to group these words under. Then, interpreting an emotional adjective (love song, relationship, anger, etc.) from the compiled result per topic. Next, comparing each song to the emotional adjectives selected to visualize which emotional adjective is closest to the words in the song. Then the songs are sorted by year and the topic of the songs are plotted year vs. number of songs in the year per topic. 

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

* Each topic is to now be read and interpreted as to select what the topic (the 10 words) could be referring to; this will be saved as a variable. 

![87AC5967-C9DD-436A-987B-7C77AD8ABB41_4_5005_c](https://user-images.githubusercontent.com/55423732/71785031-eb8be500-2fc8-11ea-9ce9-0c2eb4b99677.jpeg)

* The topic's values (relationship, distant, anger, etc.) can be visualized for each song. 

![B472F3CC-C5F1-4F4F-931D-55DA299EDB95_4_5005_c](https://user-images.githubusercontent.com/55423732/71785119-e0858480-2fc9-11ea-9d07-f550d61cc015.jpeg)

* Set a threshold in order for the set to return the values of either 0 or 1 for the topic per each song. 

![3BE8D2C3-EAF4-47AC-A8E2-66075C23D575_4_5005_c](https://user-images.githubusercontent.com/55423732/71785104-addb8c00-2fc9-11ea-807a-db3a6152b8e1.jpeg)

* The topics of each song in a given year can now be visualized and plotted as **years** vs. **topics mentioned in songs**.

![B081FE5A-AFF6-420F-9682-C1100D52C516_4_5005_c](https://user-images.githubusercontent.com/55423732/71785167-7b7e5e80-2fca-11ea-89dd-da5702fd7ccc.jpeg)


* If you made it this far, thank you for following along on my first attempt at a form of NLP using a band's lyrics. Unfortunatly it can be seen that the year 2006 may have doubled up values for songs within the csv dataset and this was not accounted for.

![D1614448-AFB9-45EB-A3DD-96730AEA5EE1](https://user-images.githubusercontent.com/55423732/71785168-820cd600-2fca-11ea-86b7-6465410463e7.jpeg)




