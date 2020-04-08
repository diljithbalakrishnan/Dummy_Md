
**Moviebuff: (Front end)** you will be able to watch the latest trailers, check out photos, access cast and crew information, read reviews, and ultimately lose yourself in the sheer volume of movie-based information at your disposal.

**Moviebuff (Back end)** you will enter the data for the movie and other details from the back end, movie details will replicated in the Moviebuff website

Movie can be classified as Bilingual and Dubbed movie

**Bilingual movies**
The same story and shotted in the different language is called bilingual movies
Ex. Neram, Bahubali

**Dubbed movies**
The same story are shotted once and convert into different language
Ex. Avenger endgame

**Movie Information**

There are several fields to be filled to create a movie

Basic details -> basic information 

Cast & crew -> cast & crew details 

Photos, videos, Audio -> photo, videos should be tagged to movies and music for the movie 

Critic reviews -> reviews about the movies

News -> news about the movie 

Tech details and trivia -> basic details of the movie such as location, aspect ratio etc..

Link -> the song and movie links for the social site

Box office -> budget details for the movie

CPLs -> composition playlist details


Assume in the movie form, if you want to add any data in the dropdown. You should
add the data from the LIST page.
 

Contribution -> the user will contribute the movie details

Movie Duplicates -> If the movie has same data will display in the duplicate page 

Untranslated shows -> shows will be there, you should map the movie 

Untranslated theatres -> assume the theaters name is misspelled, you have to map the theatre name with the correct theatre

Untranslated screens -> select the theatre and screen the movie should be played

Untranslated publication staff -> display the publication name  

Untranslated city lookup -> assume any user used our app from different country, we will store that country to db. and we can also map the city 

Untranslated CPLs -> used to map the cpl and movie 

Note: to get CPLs you can use postman

To get the CPL for the movie (We will get CPL from Qubewire)
Steps: 
- Each time give a new uuid(Generate from movie) and hit the Api
- The CPL is generated 
- Navigate to Moviebuff and Map the CPL to any movie 
- again hit the api(You will get the following result)



When changes to a parent movie are tried to publish, before publishing the changes are propagated to child movies.

When data in child movie is different than the old data in parent movie, then they are considered as conflict.

No-conflict example:

Parent One line synopsis: "This is a movie"

Child One line synopsis: "This is a movie"

In this case if we make changes to parent movie, ther are no conflict.

Conflict example:

Parent One line synopsis: "This is a good movie"

Child One line synopsis: "This is a movie"

In this case if we make changes to parent movie, it is a conflict.
