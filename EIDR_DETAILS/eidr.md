
### EXPLANATION FOR EIDR:
We are registering movies for EIDR.
For example, When the user registers the movie. In the backend, it calls the EIDR API and that movie has been created in EIDR also. that unique id is generated in EIDR. 

---

#### Missing data
In the Movie page, we are displaying some field as mandatory field (mandatory field for EIDR). For Example: Running time , title language etc. After all the conditions are fulfilled. 
the movie will be registered in EIDR.

For Example,
The user is not filled the Running time for a movie: “I”.
That “I” movie will be displayed in missing data(Moviebuff: Translations: Unmapped EIDR movies: Missing Data)
____
- Currently we are registering normal movies and bilingual movies. We are not registering dubbed movies. We can register bilingual movies up to 100.

![Snip20200227_1](https://user-images.githubusercontent.com/46953898/75470881-606f1000-59b7-11ea-9e15-271bdce6eb19.png)

---
#### Unmapped EIDR movies conflicts:
In Moviebuff: Movie: Panda

There are many EIDR movies are having the same data as Panda(Kind of duplicate)
For Example: Same combo but story and cast  different.
The EIDR will provide score based on matching data. 

In the Conflict screen: we will display the conflicts for the movie

In the Conflicts screen: There are three options:
Map, Register, Review, Ignore

If EIDR records and our records are matched. you can click the map button. The Movie will get mapped. 

If you have any doubts about the movies. you can click the review button, both the movies will send through mail. The EIDR team will review it manually. 

If there is one match for the movie. you can click register button. Automatically, the movie will get registered. 

If there is two movies, They are completely different movie, you can ignore the movie as well. You can view the ignored movie in Ignored EIDR movies screen. 


#### EIDR Status Code Details: 
0 -> Incomplete(Not filled the Mandatory fields)

1 -> Matched (if EIDR and moviebuff having same data if the score less than 85)

2 -> New Record (Infrequent, Temporary purpose only)

3 -> Approved (If the user filled all EIDR mandatory fields,  if the score is above 85, automatically the movie gets approved)

4 -> Rejected (In the Conflicts screen when the user clicks the ignore button)

5 -> Registered (We will display all the remaining movies in the pending registration and status as 5)

6 -> Failed (If the EIDR side is down, when we tries to register the movie)

7 -> Pending submission (When the user clicks the register button it will come to pending submission)


#### Explain the Status with Test flows:
Failure Status (EIDR Failures): 
when the EIDR side is down, the user tries to register the movie, it should come in Failure page
Test Flow:
- Changing the Environment Variable in Moviebuff side.
- On that time mismatch will happen in EIDR
- On that particular time, Create a new movie or Existing movie and publish it
- Note: We should fill the EIDR mandatory fields before publishing.
- That movie will come to Unmapped EIDR Movies: Failures Page


Registration status (Pending Registration): 
Steps: 
- Create a movie 'Panda'(fill all the mandatory fields)
- Assume EIDR also having same movie like panda. So it will be in status 1(match)
- but this panda movie is a different movie
- On that time the user thinks to register the movie ON EIDR
- In the Conflict screen: the user clicks the register button. the movie will go to the status 7(pending submission)
- In moviebuff: Everynight the job will run 
- The job will send the movies which are in Pending submission and EIDR will review the movie and give the status is 3(approved)
- We will display the remaining movies in the pending registration and status as 5.


---
If any outsourcing company register in EIDR, we will get the slack alert and those datas will stored in DB


