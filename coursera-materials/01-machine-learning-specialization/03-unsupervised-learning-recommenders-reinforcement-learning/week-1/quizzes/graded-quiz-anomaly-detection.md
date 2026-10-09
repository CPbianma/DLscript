---
type: graded-quiz
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 1
section: Practice quiz: Anomaly detection
item_title: Anomaly detection
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/assignment-submission/afUuX/anomaly-detection
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Anomaly detection

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

You are building a system to detect if computers in a data center are malfunctioning. You have 10,000 data points of computers functioning well, and no data from computers malfunctioning. What type of algorithm should you use?

- [x] Anomaly detection
- [ ] Supervised learning

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

You are building a system to detect if computers in a data center are malfunctioning. You have 10,000 data points of computers functioning well, and 10,000 data points of computers malfunctioning. What type of algorithm should you use?

- [ ] Anomaly detection
- [x] Supervised learning

*Points: 1 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

Say you have 5,000 examples of normal airplane engines, and 15 examples of anomalous engines. How would you use the 15 examples of anomalous engines to evaluate your anomaly detection algorithm?

- [ ] Because you have data of both normal and anomalous engines, don’t use anomaly detection. Use supervised learning instead.
- [ ] You cannot evaluate an anomaly detection algorithm because it is an unsupervised learning algorithm.
- [x] Put the data of anomalous engines (together with some normal engines) in the cross-validation and/or test sets to measure if the learned model can correctly detect anomalous engines.
- [ ] Use it during training by fitting one Gaussian model to the normal engines, and a different Gaussian model to the anomalous engines.

*Points: 1 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

Anomaly detection flags a new input xxxx as an anomaly if p(x)<ϵp(x) < \epsilonp(x)<ϵp, left parenthesis, x, right parenthesis, is less than, \epsilon. If we reduce the value of ϵ\epsilonϵ\epsilon, what happens?

- [ ] The algorithm is more likely to classify new examples as an anomaly.
- [x] The algorithm is less likely to classify new examples as an anomaly.
- [ ] The algorithm is more likely to classify some examples as an anomaly, and less likely to classify some examples as an anomaly. It depends on the example xxxx.
- [ ] The algorithm will automatically choose parameters μ\muμmu and σ\sigmaσsigma to decrease p(x)p(x)p(x)p, left parenthesis, x, right parenthesis and compensate.

*Points: 1 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

You are monitoring the temperature and vibration intensity on newly manufactured aircraft engines. You have measured 100 engines and fit the Gaussian model described in the video lectures to the data. The 100 examples and the resulting distributions are shown in the figure below.

The measurements on the latest engine you are testing have a temperature of 17.5 and a vibration intensity of 48. These are shown in magenta on the figure below. What is the probability of an engine having these two measurements?

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/0b4675ef-89e7-487f-a8a8-3e089a81a817image2.png?expiry=1791556683629&hmac=kP3bp-0L4Vv5nOJn9TwYJXcN1bhywixN9xCTR2h21F4)

- [x] 0.0738 \* 0.02288 = 0.00169
- [ ] 17.5 \* 48 = 840
- [ ] 17.5 + 48 = 65.5
- [ ] 0.0738 + 0.02288 = 0.0966

*Points: 1 / 1*

