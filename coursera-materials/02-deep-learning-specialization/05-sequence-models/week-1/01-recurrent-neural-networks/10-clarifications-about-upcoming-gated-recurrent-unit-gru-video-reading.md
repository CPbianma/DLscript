---
type: reading
specialization: Deep Learning Specialization
course: Sequence Models
week: 1
section: Recurrent Neural Networks
item_title: Clarifications about Upcoming Gated Recurrent Unit (GRU) Video
source_url: https://www.coursera.org/learn/nlp-sequence-models/supplement/XuA7H/clarifications-about-upcoming-gated-recurrent-unit-gru-video
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---
# Clarifications about Upcoming Gated Recurrent Unit (GRU) Video

Correction in "Gated Recurrent Unit (GRU)" (14:04):

The last line should use an element-wise multiplication "\*" instead of a plus sign "+".

# $$c^{<t>} = \Gamma\_{u} \* \tilde{c}^{<t>} + (1 - \Gamma\_{u}) \* c^{<t-1>}$$

See the correction in red.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/UexLI9QWEemkuwrX1d3ObA_5f5254fba838a43af2503654036c04c7_Screen-Shot-2019-09-10-at-2.58.19-PM.png?expiry=1791555225825&hmac=3aJNqDywazAx2-QJcT2Fhoj8grZiSbWDuSYNYfECgXU)
