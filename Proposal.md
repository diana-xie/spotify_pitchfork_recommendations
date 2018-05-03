# Proposal for Capstone Project

**Title:** Creating a reviewer recommendation engine to match individual consumers with compatible music critics

## Problem:

Music preferences are highly variable across individuals and genres. Despite this variability, an overwhelming number of new artists and albums are released each year - as a result, our process of discovering new favorites can rely heavily on a few reviewers and “best-of” lists. With major music review sites wielding disproportionate influence on artist popularity, an important question is whether sites such as Pitchfork (“The Most Trusted Voice in Music”) are “unbiased” in their reviews. Namely, do their reviewers display bias towards certain genres or characteristics of music?

Perhaps, whether reviewers are “unbiased” is not even the right question to ask. Matching reviewer bias with consumer preference could provide more accurate music recommendations, a domain that streaming services such as Spotify already pose a threat in as they constantly improve algorithms that automatically accomplish this task. Here, I propose creating a recommendation engine with the specific goal of generating such matches. My proposal consists of two parts. First, music critics are categorized by music preference to predict what ratings they will individually score for albums. And second, these music preference “profiles” will be used matches individual consumers with compatible music critics (the “reviewer recommendation engine”).

## Client & Pitch

There are now faster, more innovative ways for people to discover new music, and the Pitchforks of media must adapt to remain relevant and competitive in the increasingly fast-paced media landscape. Thus, they must experiment with new ideas, including methods of delivering music recommendations. My proposal integrates the type of recommendation engine that has increasingly become the norm of music discovery, along with the enduring importance of “longform” reviews that formed the original basis of readership for these sites and their continuing appeal.

As such, my target clients would be media sites that draw upon the expertise of a large set of critics to produce music reviews (and by extension, music recommendations), or a company that would be interested in producing an app/platform that utilizes such a reviewer recommendation engine.

## Data:

This project relies on two datasets: 1) Spotify audio features, and 2) Pitchfork Media’s music critics and their reviews.

The first set is drawn from Spotify’s API (https://developer.spotify.com/web-api/), which provides a detailed audio analysis of each track in their database. This audio analysis contains a standardized set of features with an accompanying score for each (ex. ‘energy’, ‘danceability’, ‘instrumentalness’).

The second set can be directly downloaded from Kaggle: https://www.kaggle.com/nolanbconaway/pitchfork-data/data.  To keep this proposal tractable for a first capstone project, I will limit the source of music reviews and their critics to Pitchfork Media. This database contains Pitchfork reviews from Jan 5, 1999 to Jan 8, 2017 and their associated information such as the artist, album, music critic, rating, and date of review.  

## Approach:

To profile critics by music preferences, each critic will be assigned a model consisting of Spotify audio track features and album genre, weighted by the rating they gave the album. These profiles can form the basis of a cluster analysis to determine whether there exist significant categories of “bias”, i.e. music preferences, among this population of critics. Based on these individual profiles and categories, an interface can then be set up in which individuals can input their preferred music and be matched with a set of music critics. As per the models used to profile each critic, the basis of this match will therefore be the weighted features of the music the individual likes, and the preferred features of the critic. In order to test the accuracy of these recommendations, reviewer data and ratings for each critic will be separated into a training, test, and validation sets in order to predict critic preference on the corresponding held-out data.

## Deliverables:
1.    Code:

	a.    Data acquisition, particularly for obtaining audio track features from the Spotify API
	b.    Data wrangling to feed information into the music critic models
	c.    Model and cluster analysis
	d.    Interface for inputting favorite albums, songs and returning set of recommended music critics to follow
	
2.    Report on the capstone project
3.    Presentation on the capstone project
