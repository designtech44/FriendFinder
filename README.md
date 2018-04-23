# FriendFinder
Node and Express Servers

In this activity, you'll build a compatibility-based "FriendFinder" application -- basically a dating app. This full-stack site will take in results from your users' surveys, then compare their answers with those from other users. The app will then display the name and picture of the user with the best overall match.

Here is the link to my Heroku deployment

https://friendfinder-44888.herokuapp.com/


### Instructions

1. Create a survey with 10 questions. Each answer should be on a scale of 1 to 5 based on how much the user agrees or disagrees with a question.

2. This app requires these npm packages: `express`, `body-parser` and `path`.

3. The `htmlRoutes.js` file should include two routes:

* A GET Route to `/survey` which should display the survey page.
* A default, catch-all route that leads to `home.html` which displays the home page.

4. The `apiRoutes.js` file should contain two routes:

* A GET route with the url `/api/friends`. This will be used to display a JSON of all possible friends.
* A POST routes `/api/friends`. This will be used to handle incoming survey results. This route will also be used to handle the compatibility logic.

5. Save the application's data inside of `app/data/friends.js` as an array of objects.

6. Determine the user's most compatible friend by:

* Converting each user's results into a simple array of numbers (ex: `[5, 1, 4, 4, 5, 1, 2, 5, 4, 1]`).
* With that done, compare the difference between current user's scores against those from other users, question by question. Add up the differences to calculate the `totalDifference`.
* Example:
* User 1: `[5, 1, 4, 4, 5, 1, 2, 5, 4, 1]`
* User 2: `[3, 2, 6, 4, 5, 1, 2, 5, 4, 1]`
* Total Difference: **2 + 1 + 2 =** **_5_**
* Remember to use the absolute value of the differences. Put another way: no negative solutions! Your app should calculate both `5-3` and `3-5` as `2`, and so on.
* The closest match will be the user with the least amount of difference.

7. Once you've found the current user's most compatible friend, display the result as a modal pop-up.
* The modal should display both the name and picture of the closest match
