
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




 


Conflict flow:

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
