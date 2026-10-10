---
type: graded-quiz
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: "Practice quiz: Collaborative filtering"
item_title: Collaborative Filtering
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/assignment-submission/yThnA/collaborative-filtering
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Collaborative Filtering

**Grade: 100%**

## Question 1 (GradedNumericQuestion)

You have the following table of movie ratings:

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| Movie | Elissa | Zach | Barry | Terry |
| Football Forever | 5 | 4 | 3 | ? |
| Pies, Pies, Pies | 1 | ? | 5 | 4 |
| Linear Algebra Live | 4 | 5 | ? | 1 |

Refer to the table above for question 1 and 2. Assume numbering starts at 1 for this quiz, so the rating for Football Forever by Elissa is at (1,1)

What is the value of nun\_unu​n, start subscript, u, end subscript


*Points: 1 / 1*

## Question 2 (GradedNumericQuestion)

What is the value of r(2,2)r(2,2)r(2,2)r, left parenthesis, 2, comma, 2, right parenthesis


*Points: 1 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

In which of the following situations will a collaborative filtering system be the most appropriate learning algorithm (compared to linear or logistic regression)?

- [ ] You're an artist and hand-paint portraits for your clients. Each client gets a different portrait (of themselves) and gives you 1-5 star rating feedback, and each client purchases at most 1 portrait. You'd like to predict what rating your next customer will give you.
- [x] You run an online bookstore and collect the ratings of many users. You want to use this to identify what books are "similar" to each other (i.e., if a user likes a certain book, what are other books that they might also like?)
- [ ] You subscribe to an online video streaming service, and are not satisfied with their movie suggestions. You download all your viewing for the last 10 years and rate each item. You assign each item a genre. Using your ratings and genre assignment, you learn to predict how you will rate new movies based on the genre.
- [ ] You manage an online bookstore and you have the book ratings from many users. You want to learn to predict the expected sales volume (number of books sold) as a function of the average rating of a book.

*Points: 1 / 1*

## Question 4 (GradedCheckboxQuestion)

For recommender systems with binary labels y, which of these are reasonable ways for defining when yyyy should be 1 for a given user jjjj and item iiii? (Check all that apply.)

- [ ] yyyy is 1 if user jjjj has not yet been shown item iiii by the recommendation engine
- [x] yyyy is 1 if user jjjj purchases item iiii (after being shown the item) ✅correct
  > Feedback: Nice work Purchasing an item shows a user's preference for that item. It also shows that an item is preferred by a user.
- [x] yyyy is 1 if user jjjj fav/likes/clicks on item iiii (after being shown the item) ✅correct
  > Feedback: Nice work fav/likes/clicks on an item shows a user's interest in that item. It also shows that an item is interesting to a user.
- [ ] yyyy is 1 if user jjjj has been shown item iiii by the recommendation engine

*Points: 1 / 1*

