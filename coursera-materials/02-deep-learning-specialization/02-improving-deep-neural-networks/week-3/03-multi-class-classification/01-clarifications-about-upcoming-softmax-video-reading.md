---
type: reading
specialization: Deep Learning Specialization
course: Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization
week: 3
section: Multi-class Classification
item_title: Clarifications about Upcoming Softmax Video
source_url: https://www.coursera.org/learn/deep-neural-network/supplement/fh9Po/clarifications-about-upcoming-softmax-video
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---
# Clarifications about Upcoming Softmax Video

Please note that in the next video at 4:30, the text for the softmax formulas mixes subscripts "j" and "i", when the subscript should just be the same (just "i") throughout the formula.

So the formula for softmax **should** be:

# $$a^{[L]} = \frac{e^{Z^{[L]}}}{\sum\_{i=1}^{4} t\_{i} }$$
