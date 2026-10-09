---
type: reading
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 4
section: Neural Style Transfer
item_title: Clarifications about Upcoming Style Cost Function Video
source_url: https://www.coursera.org/learn/convolutional-neural-networks/supplement/p9Zdf/clarifications-about-upcoming-style-cost-function-video
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---
# Clarifications about Upcoming Style Cost Function Video

Please note that in the next video at around 8:50 when Andrew wrote down the second formula of matrix, the second factor of the multiplication should be on index k' (k prime), not k (otherwise it does not calculate any kind of covariance). This is shown in black below.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/G6ZaTrzaEems6BL4PyEw_A_d0d02e11b9f0633964bd0a9ebbfeb7db_style.png?expiry=1791555168930&hmac=I4vHdOI58Yvt7_CQe8zfWSEfV6I3NiQT4wdvsTt4WZc)

So the formula should be:

### $$G\_{kk'}^{[l](G)} = \sum\_{i=1}^{n\_H}\sum\_{j=1}^{n\_W} a\_{i,j,k}^{[l](G)} a\_{i,j,k'}^{[l](G)}$$

Also at 11:08 the style cost function formula should be the squared difference:

### $$(G\_{S} - G\_{G})^{2}$$

instead of just the difference:

### $$(G\_{S} - G\_{G})$$

The style cost function should be:

### $$J\_{style}^{[l]}(S,G) = \frac{1}{ (2n\_{H}^{[l]} n\_{W}^{[l]} n\_{C}^{[l]} )^{2} } \sum\_{k}\sum\_{k'}\left ( G\_{kk'}^{[l](S)} - G\_{kk'}^{[l](G)} \right)^{2} $$
