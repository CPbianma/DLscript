---
type: graded-quiz
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: "Practice Quiz: Content-based filtering"
item_title: Content-based filtering
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/assignment-submission/Ydam1/content-based-filtering
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Content-based filtering

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

Vector xux\_uxu​x, start subscript, u, end subscript and vector xmx\_mxm​x, start subscript, m, end subscript must be of the same dimension, where xux\_uxu​x, start subscript, u, end subscript is the input features vector for a user (age, gender, etc.) xmx\_mxm​x, start subscript, m, end subscript is the input features vector for a movie (year, genre, etc.) True or false?

- [ ] True
- [x] False

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

If we find that two movies, iiii and kkkk, have vectors vm(i)v\_m^{(i)}vm(i)​v, start subscript, m, end subscript, start superscript, left parenthesis, i, right parenthesis, end superscript and vm(k)v\_m^{(k)}vm(k)​v, start subscript, m, end subscript, start superscript, left parenthesis, k, right parenthesis, end superscript that are similar to each other (i.e., ∣∣vm(i)−vm(k)∣∣||v\_m^{(i)} - v\_m^{(k)}||∣∣vm(i)​−vm(k)​∣∣vertical bar, vertical bar, v, start subscript, m, end subscript, start superscript, left parenthesis, i, right parenthesis, end superscript, minus, v, start subscript, m, end subscript, start superscript, left parenthesis, k, right parenthesis, end superscript, vertical bar, vertical bar is small), then which of the following is likely to be true? Pick the best answer.

- [ ] We should recommend to users one of these two movies, but not both.
- [ ] A user that has watched one of these two movies has probably watched the other as well.
- [x] The two movies are similar to each other and will be liked by similar users.
- [ ] The two movies are very dissimilar.

*Points: 1 / 1*

## Question 3 (GradedCheckboxQuestion)

Which of the following neural network configurations are valid for a content based filtering application? Please note carefully the dimensions of the neural network indicated in the diagram. Check all the options that apply:

- [x] ![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/62d86c86-30aa-41a3-a88b-bad03438f032image4.png?expiry=1791556769807&hmac=C5Sk7NNF_3sEdMW7SPlzOTMS1w5p8HUHVUqYnSoGwmk)  Both the user and the item networks have the same architecture ✅correct
  > Feedback: Nice work User and item networks can be the same or different sizes.
- [x] ![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/62d86c86-30aa-41a3-a88b-bad03438f032image3.png?expiry=1791556769826&hmac=8h7hsQEurjAr2MeiJtC6Dwq4teVT31LUjWakYpbkDKU)  The user and the item networks have different architectures ✅correct
  > Feedback: Nice work User and item networks can be the same or different sizes.
- [ ] ![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/62d86c86-30aa-41a3-a88b-bad03438f032image5.png?expiry=1791556769845&hmac=ELNGlDMqq1TaTNm-Uv27l666x78VA6SV2Wdqn4s2nGg)  The user vector v\_u is 32 dimensional, and the item vector v\_m is 64 dimensional
- [x] ![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/62d86c86-30aa-41a3-a88b-bad03438f032image2.png?expiry=1791556769864&hmac=CyulKdAtjuswe1kScpH6TJH-nsy0-RmqnF4cahAeisQ)  The user and item networks have 64 dimensional v\_u and v\_m vector respectively ✅correct
  > Feedback: Nice work Feature vectors can be any size so long as 𝑣 𝑢 v u ​ v, start subscript, u, end subscript and 𝑣 𝑚 v m ​ v, start subscript, m, end subscript are the same size.

*Points: 1 / 1*

## Question 4 (GradedCheckboxQuestion)

You have built a recommendation system to retrieve musical pieces from a large database of music, and have an algorithm that uses separate retrieval and ranking steps. If you modify the algorithm to add more musical pieces to the retrieved list (i.e., the retrieval step returns more items), which of these are likely to happen? Check all that apply.

- [x] The system’s response time might increase (i.e., users have to wait longer to get recommendations) ✅correct
  > Feedback: Nice work A larger retrieval list may take longer to process which mayincrease response time.
- [ ] The system’s response time might decrease (i.e., users get recommendations more quickly)
- [ ] The quality of recommendations made to users should stay the same or worsen.
- [x] The quality of recommendations made to users should stay the same or improve. ✅correct
  > Feedback: Nice work A larger retrieval list gives the ranking system more options to choose from which should maintain or improve recommendations.

*Points: 1 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

To speed up the response time of your recommendation system, you can pre-compute the vectors v\_m for all the items you might recommend. This can be done even before a user logs in to your website and even before you know the xux\_uxu​x, start subscript, u, end subscript or vuv\_uvu​v, start subscript, u, end subscript vector. True/False?

- [ ] True
- [x] False

*Points: 0 / 1*

