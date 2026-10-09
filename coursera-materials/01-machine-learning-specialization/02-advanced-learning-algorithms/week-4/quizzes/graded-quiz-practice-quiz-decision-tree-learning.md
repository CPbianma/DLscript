---
type: graded-quiz
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: "Practice quiz: Decision tree learning"
item_title: "Practice quiz: Decision tree learning"
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/assignment-submission/1gwEW/practice-quiz-decision-tree-learning
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Practice quiz: Decision tree learning

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/f1fed11a-1ade-4b8c-b5cf-e6f9b11a2b23image4.png?expiry=1791556563506&hmac=x3wUvMJzhnbTDAsGypozGht8tqaZdBbruQbp3vHgAxc)

Recall that entropy was defined in lecture as H(p\_1) = - p\_1 log\_2(p\_1) - p\_0 log\_2(p\_0), where p\_1 is the fraction of positive examples and p\_0 the fraction of negative examples.

At a given node of a decision tree, , 6 of 10 examples are cats and 4 of 10 are not cats. Which expression calculates the entropy H(p1)H(p\_1)H(p1​)H, left parenthesis, p, start subscript, 1, end subscript, right parenthesis of this group of 10 animals?

- [ ] (0.6)log2(0.6)+(1−0.4)log2(1−0.4)(0.6) log\_2(0.6) + (1 - 0.4)log\_2(1 - 0.4)(0.6)log2​(0.6)+(1−0.4)log2​(1−0.4)left parenthesis, 0, point, 6, right parenthesis, l, o, g, start subscript, 2, end subscript, left parenthesis, 0, point, 6, right parenthesis, plus, left parenthesis, 1, minus, 0, point, 4, right parenthesis, l, o, g, start subscript, 2, end subscript, left parenthesis, 1, minus, 0, point, 4, right parenthesis
- [x] −(0.6)log2(0.6)−(0.4)log2(0.4)-(0.6) log\_2(0.6) - (0.4)log\_2(0.4)−(0.6)log2​(0.6)−(0.4)log2​(0.4)minus, left parenthesis, 0, point, 6, right parenthesis, l, o, g, start subscript, 2, end subscript, left parenthesis, 0, point, 6, right parenthesis, minus, left parenthesis, 0, point, 4, right parenthesis, l, o, g, start subscript, 2, end subscript, left parenthesis, 0, point, 4, right parenthesis
- [ ] (0.6)log2(0.6)+(0.4)log2(0.4)(0.6) log\_2(0.6) + (0.4)log\_2(0.4)(0.6)log2​(0.6)+(0.4)log2​(0.4)left parenthesis, 0, point, 6, right parenthesis, l, o, g, start subscript, 2, end subscript, left parenthesis, 0, point, 6, right parenthesis, plus, left parenthesis, 0, point, 4, right parenthesis, l, o, g, start subscript, 2, end subscript, left parenthesis, 0, point, 4, right parenthesis
- [ ] −(0.6)log2(0.6)−(1−0.4)log2(1−0.4)-(0.6) log\_2(0.6) - (1 - 0.4)log\_2(1 - 0.4)−(0.6)log2​(0.6)−(1−0.4)log2​(1−0.4)minus, left parenthesis, 0, point, 6, right parenthesis, l, o, g, start subscript, 2, end subscript, left parenthesis, 0, point, 6, right parenthesis, minus, left parenthesis, 1, minus, 0, point, 4, right parenthesis, l, o, g, start subscript, 2, end subscript, left parenthesis, 1, minus, 0, point, 4, right parenthesis

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/f1fed11a-1ade-4b8c-b5cf-e6f9b11a2b23image2.png?expiry=1791556563524&hmac=7mFXNzrIsUsKQJMF0WpcM8xGZDWzHB87lTwqyVUUUj4)

Recall that information was defined as follows:

H(p1root)−(wleftH(p1left)+wrightH(p1right))H(p\_1^{root}) - \left ( w^{left} H(p\_1^{left}) + w^{right} H(p\_1^{right}) \right ) H(p1root​)−(wleftH(p1left​)+wrightH(p1right​))H, left parenthesis, p, start subscript, 1, end subscript, start superscript, r, o, o, t, end superscript, right parenthesis, minus, left parenthesis, w, start superscript, l, e, f, t, end superscript, H, left parenthesis, p, start subscript, 1, end subscript, start superscript, l, e, f, t, end superscript, right parenthesis, plus, w, start superscript, r, i, g, h, t, end superscript, H, left parenthesis, p, start subscript, 1, end subscript, start superscript, r, i, g, h, t, end superscript, right parenthesis, right parenthesis

Before a split, the entropy of a group of 5 cats and 5 non-cats is H(5/10)H(5/10) H(5/10)H, left parenthesis, 5, slash, 10, right parenthesis. After splitting on a particular feature, a group of 7 animals (4 of which are cats) has an entropy of H(4/7)H(4/7)H(4/7)H, left parenthesis, 4, slash, 7, right parenthesis. The other group of 3 animals (1 is a cat) and has an entropy of H(1/3)H(1/3)H(1/3)H, left parenthesis, 1, slash, 3, right parenthesis. What is the expression for information gain?

- [ ] H(0.5)−(7∗H(4/7)+3∗H(1/3))H(0.5) - \left ( 7 \* H(4/7) + 3 \* H(1/3) \right )H(0.5)−(7∗H(4/7)+3∗H(1/3))H, left parenthesis, 0, point, 5, right parenthesis, minus, left parenthesis, 7, times, H, left parenthesis, 4, slash, 7, right parenthesis, plus, 3, times, H, left parenthesis, 1, slash, 3, right parenthesis, right parenthesis
- [x] H(0.5)−(710H(4/7)+310H(1/3))H(0.5) - \left ( \frac{7}{10} H(4/7) + \frac{3}{10} H(1/3) \right )H(0.5)−(107​H(4/7)+103​H(1/3))H, left parenthesis, 0, point, 5, right parenthesis, minus, left parenthesis, start fraction, 7, divided by, 10, end fraction, H, left parenthesis, 4, slash, 7, right parenthesis, plus, start fraction, 3, divided by, 10, end fraction, H, left parenthesis, 1, slash, 3, right parenthesis, right parenthesis
- [ ] H(0.5)−(47∗H(4/7)+47∗H(1/3))H(0.5) - \left ( \frac{4}{7} \* H(4/7) + \frac{4}{7} \* H(1/3) \right )H(0.5)−(74​∗H(4/7)+74​∗H(1/3))H, left parenthesis, 0, point, 5, right parenthesis, minus, left parenthesis, start fraction, 4, divided by, 7, end fraction, times, H, left parenthesis, 4, slash, 7, right parenthesis, plus, start fraction, 4, divided by, 7, end fraction, times, H, left parenthesis, 1, slash, 3, right parenthesis, right parenthesis
- [ ] H(0.5)−(H(4/7)+H(1/3))H(0.5) - \left ( H(4/7) + H(1/3) \right )H(0.5)−(H(4/7)+H(1/3))H, left parenthesis, 0, point, 5, right parenthesis, minus, left parenthesis, H, left parenthesis, 4, slash, 7, right parenthesis, plus, H, left parenthesis, 1, slash, 3, right parenthesis, right parenthesis

*Points: 1 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/f1fed11a-1ade-4b8c-b5cf-e6f9b11a2b23image5.png?expiry=1791556563546&hmac=UxmxAdAuEjxrkTMLwMDll9NULirJvaffzXwFTSL_2oA)

To represent 3 possible values for the ear shape, you can define 3 features for ear shape: pointy ears, floppy ears, oval ears. For an animal whose ears are not pointy, not floppy, but are oval, how can you represent this information as a feature vector?

- [ ] [1,0,0]
- [ ] [1, 1, 0]
- [x] [0, 0, 1]
- [ ] [0, 1, 0]

*Points: 1 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/f1fed11a-1ade-4b8c-b5cf-e6f9b11a2b23image6.png?expiry=1791556563565&hmac=hJS9KgaYS2JAl2yXMTVFA-1oSr9V4K39ZdKzkG-TPDg)

For a continuous valued feature (such as weight of the animal), there are 10 animals in the dataset. According to the lecture, what is the recommended way to find the best split for that feature?

- [ ] Use a one-hot encoding to turn the feature into a discrete feature vector of 0’s and 1’s, then apply the algorithm we had discussed for discrete features.
- [ ] Use gradient descent to find the value of the split threshold that gives the highest information gain.
- [x] Choose the 9 mid-points between the 10 examples as possible splits, and find the split that gives the highest information gain.
- [ ] Try every value spaced at regular intervals (e.g., 8, 8.5, 9, 9.5, 10, etc.) and find the split that gives the highest information gain.

*Points: 1 / 1*

## Question 5 (GradedCheckboxQuestion)

Which of these are commonly used criteria to decide to stop splitting? (Choose two.)

- [ ] When the information gain from additional splits is too large
- [x] When the number of examples in a node is below a threshold ✅correct
  > Feedback: Nice work Yes!
- [x] When the tree has reached a maximum depth ✅correct
  > Feedback: Nice work Yes!
- [ ] When a node is 50% one class and 50% another class (highest possible value of entropy)

*Points: 1 / 1*

