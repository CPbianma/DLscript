---
type: graded-quiz
specialization: Deep Learning Specialization
course: Sequence Models
week: 4
section: Quiz
item_title: Transformers  
source_url: https://www.coursera.org/learn/nlp-sequence-models/assignment-submission/nMEml/transformers
language: en
extracted_at: 2026-10-09T16:39:49+08:00
grade: None
status: success
---
# Transformers  

## Question 1 (MultipleChoiceQuestion)

A Transformer Network, unlike its predecessors RNNs, GRUs and LSTMs, can process entire sentences all at the same time. (Parallel architecture).

- [ ] False
- [ ] True

## Question 2 (MultipleChoiceQuestion)

Transformer Network methodology is taken from:

- [ ] Attention Mechanism and RNN style of processing.
- [ ] GRUs and LSTMs
- [ ] RNN and LSTMs
- [ ] Attention Mechanism and CNN style of processing.

## Question 3 (MultipleChoiceQuestion)

How does the Self-Attention mechanism of transformers use neighboring words to compute a word’s context?

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/8e44eb51-e9a9-4d0d-b9d3-268d54fedcef_2c0b7e85b2d9486cb83db4a372b0b311_e3fa32a1-3970-4486-a06c-11167ccc9b22image1.png?expiry=1791621533532&hmac=iLnmQ0KmUa8ecDj9uNJF2r-Hg-uMGVU89GUuGKysK2o)

- [ ] Summation of the word values to map the Attention related to that given word.
- [ ] Multiplication of the word values to map the Attention related to that given word.
- [ ] Selecting the maximum word values to map the Attention related to that given word.
- [ ] Selecting the minimum word values to map the Attention related to that given word.

## Question 4 (MultipleChoiceQuestion)

Which of the following correctly represents *Attention*?

- [ ] A(Q,K,V)=∑i(exp⁡(q∗v<i>)∑jexp⁡(q∗v<j>))∗K<i>{A(Q,K,V)} = {\sum}\_i(\frac{\exp(q \* v^{<i>})} {{\sum}\_j\exp(q \* v^{<j>})})\* K^{<i>}A(Q,K,V)=∑i​(∑j​exp(q∗v<j>)exp(q∗v<i>)​)∗K<i>A, left parenthesis, Q, comma, K, comma, V, right parenthesis, equals, sum, start subscript, i, end subscript, left parenthesis, start fraction, \exp, left parenthesis, q, times, v, start superscript, is less than, i, is greater than, end superscript, right parenthesis, divided by, sum, start subscript, j, end subscript, \exp, left parenthesis, q, times, v, start superscript, is less than, j, is greater than, end superscript, right parenthesis, end fraction, right parenthesis, times, K, start superscript, is less than, i, is greater than, end superscript
- [ ] A(Q,K,V)=∑i(exp⁡(q∗k<i>)∑jexp⁡(q∗k<j>))∗∑ivi{A(Q,K,V)} = {\sum}\_i(\frac{\exp(q \* k^{<i>})} {{\sum}\_j\exp(q \* k^{<j>})})\* {\sum}\_i{v}^{i}A(Q,K,V)=∑i​(∑j​exp(q∗k<j>)exp(q∗k<i>)​)∗∑i​viA, left parenthesis, Q, comma, K, comma, V, right parenthesis, equals, sum, start subscript, i, end subscript, left parenthesis, start fraction, \exp, left parenthesis, q, times, k, start superscript, is less than, i, is greater than, end superscript, right parenthesis, divided by, sum, start subscript, j, end subscript, \exp, left parenthesis, q, times, k, start superscript, is less than, j, is greater than, end superscript, right parenthesis, end fraction, right parenthesis, times, sum, start subscript, i, end subscript, v, start superscript, i, end superscript
- [ ] A(Q,K,V)=∑i(exp⁡(q∗k<i>)∑jexp⁡(q∗k<j>))∗V<i>{A(Q,K,V)} = {\sum}\_i(\frac{\exp(q \* k^{<i>})} {{\sum}\_j\exp(q \* k^{<j>})})\* V^{<i>}A(Q,K,V)=∑i​(∑j​exp(q∗k<j>)exp(q∗k<i>)​)∗V<i>A, left parenthesis, Q, comma, K, comma, V, right parenthesis, equals, sum, start subscript, i, end subscript, left parenthesis, start fraction, \exp, left parenthesis, q, times, k, start superscript, is less than, i, is greater than, end superscript, right parenthesis, divided by, sum, start subscript, j, end subscript, \exp, left parenthesis, q, times, k, start superscript, is less than, j, is greater than, end superscript, right parenthesis, end fraction, right parenthesis, times, V, start superscript, is less than, i, is greater than, end superscript
- [ ] A(Q,K,V)=(exp⁡(q∗k<i>)exp⁡(q∗k<j>))∗V<i>{A(Q,K,V)} = (\frac{\exp(q \* k^{<i>})} {\exp(q \* k^{<j>})})\* V^{<i>}A(Q,K,V)=(exp(q∗k<j>)exp(q∗k<i>)​)∗V<i>A, left parenthesis, Q, comma, K, comma, V, right parenthesis, equals, left parenthesis, start fraction, \exp, left parenthesis, q, times, k, start superscript, is less than, i, is greater than, end superscript, right parenthesis, divided by, \exp, left parenthesis, q, times, k, start superscript, is less than, j, is greater than, end superscript, right parenthesis, end fraction, right parenthesis, times, V, start superscript, is less than, i, is greater than, end superscript

## Question 5 (MultipleChoiceQuestion)

Which of the following statements represents Key (K) as used in the self-attention calculation?

- [ ] K = specific representations of words given a Q
- [ ] K = interesting questions about the words in a sentence
- [ ] K = qualities of words given a Q
- [ ] K = the order of the words in a sentence

## Question 6 (MultipleChoiceQuestion)

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/82e3ec1a-5343-4dbf-a42e-a3b0d8569669_e38c2a115d5e4732a8093f7d14b9f13b_e3fa32a1-3970-4486-a06c-11167ccc9b22image2.png?expiry=1791621533546&hmac=C1K8aQP9diveX1Vxw-dRgajfKOU-Es-d3gQP-HiXQJ0)

iiii here represents the computed attention weight matrix associated with the ithithithi, t, h “word” in a sentence.

- [ ] False
- [ ] True

## Question 7 (MultipleChoiceQuestion)

Following is the architecture within a Transformer Network ***(without displaying positional encoding and output layers(s)).***

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/2b5162d3-3a23-4940-8b50-da05602cfcd9_2371aa34e49342f99e9ff7fd14e81fad_e3fa32a1-3970-4486-a06c-11167ccc9b22image3.png?expiry=1791621533560&hmac=zkrSCRd5CJ8mmzUZKnIvDkQ4VkWmLjfa2UHKZm1_L50)

What is generated from the output of the *Decoder’s* first block of *Multi-Head Attention*?

- [ ] V
- [ ] Q
- [ ] K

## Question 8 (MultipleChoiceQuestion)

Following is the architecture within a Transformer Network. ***(without displaying positional encoding and output layers(s))***

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/52fac881-7c8d-4009-b7d9-35476b8cd982_43bcb60380104e61950ff5b52c612e3d_e3fa32a1-3970-4486-a06c-11167ccc9b22image5.png?expiry=1791621533575&hmac=5Zo4AJGFheoIVveiEj_qV3JvpcdJWAxVd9589bMbelw)

What is the output layer(s) of the *Decoder* ? (Marked YYYY, pointed by the independent arrow)

- [ ] Softmax layer
- [ ] Softmax layer followed by a linear layer.
- [ ] Linear layer followed by a softmax layer.
- [ ] Linear layer

## Question 9 (CheckboxQuestion(checkbox))

Why is positional encoding important in the translation process? (Check all that apply)

- [ ] Position and word order are essential in sentence construction of any language.
- [ ] It helps to locate every word within a sentence.
- [ ] It is used in CNN and works well there.
- [ ] Providing extra information to our model.

## Question 10 (CheckboxQuestion(checkbox))

Which of these is a good criterion for a good positional encoding algorithm?

- [ ] It should output a unique encoding for each time-step (word’s position in a sentence).
- [ ] Distance between any two time-steps should be consistent for all sentence lengths.
- [ ] The algorithm should be able to generalize to longer sentences.
- [ ] None of these.

