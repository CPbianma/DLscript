---
type: reading
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 1
section: Convolutional Neural Networks
item_title: Clarifications about Upcoming Why Convolutions?
source_url: https://www.coursera.org/learn/convolutional-neural-networks/supplement/mficY/clarifications-about-upcoming-why-convolutions
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---
# Clarifications about Upcoming Why Convolutions?

Starting around 2:15 minute, the number of parameters should have been:

(5 \* 5 \* 3 + 1) \* 6 = 456

This is based on the equation:

$$(f^{[l]} \times f^{[l]} \times n\_{c}^{[l-1]} + 1) \times n\_{c}^{[l]}$$.

$$f^{[l]}$$ is the filter height (and width).

$$n\_{c}^{[l-1]}$$ is the number of channels in the previous layer.

$$n\_{c}^{[l]}$$ is the number of channels in the current layer.

The "1" is the bias term.

(It was (5 \* 5 + 1) \* 6 = 156 in the video.)
