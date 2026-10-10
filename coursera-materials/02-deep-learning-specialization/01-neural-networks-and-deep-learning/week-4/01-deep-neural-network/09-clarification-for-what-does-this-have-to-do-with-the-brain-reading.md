---
type: reading
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 4
section: Deep Neural Network
item_title: "Clarification For: What does this have to do with the brain?"
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/supplement/E79Uh/clarification-for-what-does-this-have-to-do-with-the-brain
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---
# Clarification For: What does this have to do with the brain?

Note that the formulas shown in the next video have a few typos. Here is the correct set of formulas.

$$dZ^{[L]} = A^{[L]} - Y$$

$$dW^{[L]} = \frac{1}{m}dZ^{[L]}{A^{[L-1]^{T}}}$$

$$db^{[L]} = \frac{1}{m} np.sum(dZ^{[L]}, axis=1, keepdims=True)$$

$$dZ^{[L-1]} = W^{[L]^{T}}dZ^{[L]} \* g'^{[L-1]}(Z^{[L-1]})$$

Note that \* denotes element-wise multiplication)

$$\vdots$$

$$dZ^{[1]} = W^{[2]^{T}}dZ^{[2]} \* g'^{[1]}(Z^{[1]})$$

$$dW^{[1]} = \frac{1}{m}dZ^{[1]}A^{[0]^{T}}$$

Note that $$A^{[0]^{T}}$$ is another way to denote the input features, which is also written as $$X^{T}$$

$$db^{[1]} = \frac{1}{m} np.sum(dZ^{[1]}, axis=1, keepdims=True)$$
