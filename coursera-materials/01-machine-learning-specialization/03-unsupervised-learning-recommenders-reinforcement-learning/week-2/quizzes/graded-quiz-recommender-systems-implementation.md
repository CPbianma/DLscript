---
type: graded-quiz
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Practice quiz: Recommender systems implementation
item_title: Recommender systems implementation
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/assignment-submission/Bz0pI/recommender-systems-implementation
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Recommender systems implementation

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

Lecture described using ‘mean normalization’ to do feature scaling of the ratings. What equation below best describes this algorithm?

- [ ] ynorm(i,j)μiσ2i=y(i,j)−μiσiwhere=1∑jr(i,j)∑j:r(i,j)=1y(i,j)=1∑jr(i,j)∑j:r(i,j)=1(y(i,j)−μj)2\begin{align}y\_{norm}(i,j) &= \frac {y(i,j) - \mu\_i}{\sigma\_i} \quad \text{where}\\ \mu\_i &= \frac{1}{\sum\_{j} r(i,j)} \sum\_{j:r(i,j)=1} y(i,j) \\ \sigma^2\_i &= \frac{1}{\sum\_{j} r(i,j)} \sum\_{j:r(i,j)=1} (y(i,j) - \mu\_j)^2 \end{align}
- [x] ynorm(i,j)μi=y(i,j)−μiwhere=1∑jr(i,j)∑j:r(i,j)=1y(i,j)\begin{align}y\_{norm}(i,j) &= y(i,j) - \mu\_i \quad \quad \text{where}\\ \mu\_i &= \frac{1}{\sum\_{j} r(i,j)} \sum\_{j:r(i,j)=1} y(i,j) \end{align}
- [ ] ynorm(i,j)μi=y(i,j)−μimaxi−miniwhere=1∑jr(i,j)∑j:r(i,j)=1y(i,j)\begin{align}y\_{norm}(i,j) &= \frac {y(i,j) - \mu\_i}{max\_i - min\_i} \quad \text{where}\\ \mu\_i &= \frac{1}{\sum\_{j} r(i,j)} \sum\_{j:r(i,j)=1} y(i,j) \end{align}

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

The implementation of collaborative filtering utilized a custom training loop in TensorFlow. Is it true that TensorFlow always requires a custom training loop?

- [ ] Yes. TensorFlow gains flexibility by providing the user primitive operations they can combine in many ways.
- [x] No: TensorFlow provides simplified training operations for some applications.

*Points: 1 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

Once a model is trained, the 'distance' between features vectors gives an indication of how similar items are.

The squared distance between the two vectors x(k)\mathbf{x}^{(k)}x(k)x, start superscript, left parenthesis, k, right parenthesis, end superscript and x(i)\mathbf{x}^{(i)}x(i)x, start superscript, left parenthesis, i, right parenthesis, end superscript is:

distance=∥x(k)−x(i)∥2=∑l=1n(xl(k)−xl(i))2 distance = \left\Vert \mathbf{x^{(k)}} - \mathbf{x^{(i)}} \right\Vert^2 = \sum\_{l=1}^{n}(x\_l^{(k)} -x\_l^{(i)})^2distance=∥∥∥​x(k)−x(i)∥∥∥​2=∑l=1n​(xl(k)​−xl(i)​)2d, i, s, t, a, n, c, e, equals, \Vert, x, start superscript, left parenthesis, k, right parenthesis, end superscript, minus, x, start superscript, left parenthesis, i, right parenthesis, end superscript, \Vert, squared, equals, sum, start subscript, l, equals, 1, end subscript, start superscript, n, end superscript, left parenthesis, x, start subscript, l, end subscript, start superscript, left parenthesis, k, right parenthesis, end superscript, minus, x, start subscript, l, end subscript, start superscript, left parenthesis, i, right parenthesis, end superscript, right parenthesis, squared

Using the table below, find the closest item to the movie "Pies, Pies, Pies".

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| Movie | User 1 | … | User n | x0x\_0x0​x, start subscript, 0, end subscript | x1x\_1x1​x, start subscript, 1, end subscript | x2x\_2x2​x, start subscript, 2, end subscript |
| Pastries for Supper |  |  |  | 2.0 | 2.0 | 1.0 |
| Pies, Pies, Pies |  |  |  | 2.0 | 3.0 | 4.0 |
| Pies and You |  |  |  | 5.0 | 3.0 | 4.0 |

- [ ] Pastries for Supper
- [x] Pies and You

*Points: 9.1 / 1*

## Question 4 (GradedCheckboxQuestion)

Which of these is an example of the cold start problem? (Check all that apply.)

- [ ] A recommendation system takes so long to train that users get bored and leave.
- [x] A recommendation system is unable to give accurate rating predictions for a new product that no users have rated. ✅correct
  > Feedback: Nice work A recommendation system uses product feedback to fit the prediction model.
- [x] A recommendation system is unable to give accurate rating predictions for a new user that has rated few products. ✅correct
  > Feedback: Nice work A recommendation system uses user feedback to fit the prediction model.
- [ ] A recommendation system is so computationally expensive that it causes your computer CPU to heat up, causing your computer to need to be cooled down and restarted.

*Points: 1 / 1*

