# A Spotify-Pitchfork integrated recommendation engine

Flask app, based on this project: [dianaxie.pythonanywhere.com](dianaxie.pythonanywhere.com)

## In this project, I create a reviewer recommendation engine to match individual consumers with compatible music critics.

### Background
Music preferences are highly variable across individuals and genres. Despite this variability, an overwhelming number of new artists and albums are released each year and as a result our process of discovering new favorites can rely heavily on a few reviewers and “best-of” lists. With disproportionate influence on artist popularity, an important question is whether major music review sites such as Pitchfork (“The Most Trusted Voice in Music”) are “unbiased” in their reviews. 

Namely, do they display favorable (or unfavorable) bias towards certain characteristics present in music, and can these characteristics be used to profile different types of reviewers? Perhaps, whether reviewers are “unbiased” is not even the right question to ask. Matching reviewer bias with consumer preference could provide more accurate music recommendations, a domain that streaming services such as Spotify already pose a threat in as they constantly improve algorithms that automatically accomplish this task.
 
### Project 
In this project, I categorize Pitchfork Media music critics by their music feature preferences (ex. 'danceability', 'energy', 'instrumentalness') to predict what ratings they will reward albums. I then produce a proof-of-concept recommendation engine that can match a user to a music critic or cluster of critics on Pitchfork, based on similiar music tastes.

### Results 

#### "Best-cluster"-picking algorithm and linear regression cross-validation

I wrangled Pitchfork and Spotify data to cluster all music critics who reviewed an album for Pitchfork between 1999-2017. This was accomplished by integrating their album ratings with Spotify-provided album audio features.<p>
 
Although only a handful of useful clusters were generated, I was still able to set up an
automated process for picking tight clusters and combining linear regression as a form of
cross-validation to check that they were of practical use and actually incorporated critics with
similar musical preferences.<p>

#### A two-fold recommendation engine
In the end, I revised this recommendation engine to first recommend the user’s most-similar
critic (first-choice critic) and then a list of secondary recommendations that contained the
remaining critics in the first-choice critic’s cluster. My approach was to prioritize recommending
the most similar critic to the user, rather than having the usefulness of this recommendation be
washed out by simply recommending an entire list (cluster) of critics that likely did not generalize
as well (based on my cross-validation findings on critics held-out from the cluster sample).<p>

#### Summary
In conclusion, I was able to set up a pipeline for integrating static data (Pitchfork SQL
review/critic data extracted from Nolan Conaway's Kaggle [dataset](https://www.kaggle.com/nolanbconaway/pitchfork-data)) with that of an [API (Spotify)](https://developer.spotify.com/documentation/web-api/reference/tracks/get-audio-features/). I used this
information to build a unique recommendation engine that recommended music critics, rather
than the typical music track recommendation engine. Although more data is likely needed to
refine the accuracy of this recommendation engine, it was still able to perform well in a few
cases and in the least provided at least 1 reliable music critic recommendation.
