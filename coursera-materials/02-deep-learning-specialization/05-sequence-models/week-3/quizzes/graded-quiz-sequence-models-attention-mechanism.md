---
type: graded-quiz
specialization: Deep Learning Specialization
course: Sequence Models
week: 3
section: Quiz
item_title: Sequence Models & Attention Mechanism  
source_url: https://www.coursera.org/learn/nlp-sequence-models/assignment-submission/SFJH7/sequence-models-attention-mechanism
language: en
extracted_at: 2026-10-09T16:36:32+08:00
grade: None
status: success
---
# Sequence Models & Attention Mechanism  

## Question 1 (MultipleChoiceQuestion)

Consider using this encoder-decoder model for machine translation.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/eddd1155-bd5e-4e6c-b7d6-976b26f0c52e_25da5fa839654b0e8e01dfeb82625f63_9aaaa515-0509-4bad-aea6-868704adc89dimage2.png?expiry=1791621233219&hmac=Sh333_kywstgW9_x-Pd5QU-LaNozSdOmkbD7rMvpr6k)

True/False: This model is a “conditional language model” in the sense that the decoder portion (shown in purple) is modeling the probability of the output sentence yyyy given the input sentence xxxx.

- [ ] True
- [ ] False

## Question 2 (CheckboxQuestion(checkbox))

In beam search, if you decrease the beam width BBBB, which of the following would you expect to be true? Select all that apply.

- [ ] Beam search will converge after fewer steps.
- [ ] Beam search will run more quickly.
- [ ] Beam search will generally find better solutions (i.e. do a better job maximizing *P*(*y*∣*x*)).
- [ ] Beam search will use up more memory.

## Question 3 (MultipleChoiceQuestion)

In machine translation, if we carry out beam search without using sentence normalization, the algorithm will tend to output overly short translations.

- [ ] True
- [ ] False

## Question 4 (MultipleChoiceQuestion)

Suppose you are building a speech recognition system, which uses an RNN model to map from audio clip xxxx to a text transcript yyyy. Your algorithm uses beam search to try to find the value of yyyy that maximizes P(y∣x)P(y \mid x)P(y∣x)P, left parenthesis, y, \mid, x, right parenthesis.

On a dev set example, given an input audio clip, your algorithm outputs the transcript y^=\hat{y}=y^​=y, with, hat, on top, equals “I’m building an A Eye system in Silly con Valley.”, whereas a human gives a much superior transcript y∗=y^\* =y∗=y, start superscript, times, end superscript, equals “I’m building an AI system in Silicon Valley.”

According to your model,

P(y^∣x)=1.09∗10−7P(\hat{y} \mid x) = 1.09\*10^-7P(y^​∣x)=1.09∗10−7P, left parenthesis, y, with, hat, on top, \mid, x, right parenthesis, equals, 1, point, 09, times, 10, start superscript, minus, end superscript, 7

P(y∗∣x)=7.21∗10−8P(y^\* \mid x) = 7.21\*10^-8P(y∗∣x)=7.21∗10−8P, left parenthesis, y, start superscript, times, end superscript, \mid, x, right parenthesis, equals, 7, point, 21, times, 10, start superscript, minus, end superscript, 8

Would you expect increasing the beam width B to help correct this example?

- [ ] No, because P(y∗∣x)≤P(y^∣x)P(y^\* \mid x) \leq P(\hat{y} \mid x)P(y∗∣x)≤P(y^​∣x)P, left parenthesis, y, start superscript, times, end superscript, \mid, x, right parenthesis, is less than or equal to, P, left parenthesis, y, with, hat, on top, \mid, x, right parenthesis indicates the error should be attributed to the RNN rather than to the search algorithm.
- [ ] No, because P(y∗∣x)≤P(y^∣x)P(y^\* \mid x) \leq P(\hat{y} \mid x)P(y∗∣x)≤P(y^​∣x)P, left parenthesis, y, start superscript, times, end superscript, \mid, x, right parenthesis, is less than or equal to, P, left parenthesis, y, with, hat, on top, \mid, x, right parenthesis indicates the error should be attributed to the search algorithm rather than to the RNN.
- [ ] Yes, because P(y∗∣x)≤P(y^∣x)P(y^\* \mid x) \leq P(\hat{y} \mid x)P(y∗∣x)≤P(y^​∣x)P, left parenthesis, y, start superscript, times, end superscript, \mid, x, right parenthesis, is less than or equal to, P, left parenthesis, y, with, hat, on top, \mid, x, right parenthesis indicates the error should be attributed to the RNN rather than to the search algorithm.
- [ ] Yes, because P(y∗∣x)≤P(y^∣x)P(y^\* \mid x) \leq P(\hat{y} \mid x)P(y∗∣x)≤P(y^​∣x)P, left parenthesis, y, start superscript, times, end superscript, \mid, x, right parenthesis, is less than or equal to, P, left parenthesis, y, with, hat, on top, \mid, x, right parenthesis indicates the error should be attributed to the search algorithm rather than to the RNN.

## Question 5 (MultipleChoiceQuestion)

Suppose you are building a speech recognition system, which uses an RNN model to map from audio clip xxxx to a text transcript yyyy. Your algorithm uses beam search to try to find the value of y that maximizes P(y∣x)P(y \mid x)P(y∣x)P, left parenthesis, y, \mid, x, right parenthesis.

Suppose you work on your algorithm for a few more weeks, and now find that for the vast majority of examples on which your algorithm makes a mistake, P(y∗∣x)>P(y^∣x) P(y^\* \mid x) > P(\hat{y} \mid x)P(y∗∣x)>P(y^​∣x)P, left parenthesis, y, start superscript, times, end superscript, \mid, x, right parenthesis, is greater than, P, left parenthesis, y, with, hat, on top, \mid, x, right parenthesis. This suggests you should focus your attention on improving the RNN.

- [ ] False
- [ ] True

## Question 6 (CheckboxQuestion(checkbox))

Consider the attention model for machine translation.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/3cc87539-be5f-486f-9f7f-24e80f396532_4f7407484570411f963cc6c6a43b11af_9aaaa515-0509-4bad-aea6-868704adc89dimage3.png?expiry=1791621233232&hmac=KYTloeKwgcObt2_zfBdBGIScgQlAKoTmlXcBG2rEd6U)

Further, here is the formula for α<t,t’>\alpha^{<t,t’>}α<t,t’>alpha, start superscript, is less than, t, comma, t, ’, is greater than, end superscript.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/1ce38bf6-0bae-4648-91ae-eae060b6cf22_94a352364c36414d9e638534550f3591_9aaaa515-0509-4bad-aea6-868704adc89dimage4.png?expiry=1791621233232&hmac=-WbonZEiK8oErAT9d2hXiEvNS-4UAd0z2SzU3K1sxGY)

Which of the following statements about α<t,t’>\alpha^{<t,t’>}α<t,t’>alpha, start superscript, is less than, t, comma, t, ’, is greater than, end superscript are true? Check all that apply.

- [ ] ∑t’α<t,t’>=1\sum\_{t’} \alpha^{<t,t’>} = 1∑t’​α<t,t’>=1sum, start subscript, t, ’, end subscript, alpha, start superscript, is less than, t, comma, t, ’, is greater than, end superscript, equals, 1. (**Note the summation is over t’.**)
- [ ] ∑t’α<t,t’>=0\sum\_{t’} \alpha^{<t,t’>} = 0∑t’​α<t,t’>=0sum, start subscript, t, ’, end subscript, alpha, start superscript, is less than, t, comma, t, ’, is greater than, end superscript, equals, 0. (**Note the summation is over t’.**)
- [ ] We expect α<t,t’>\alpha^{<t,t’>}α<t,t’>alpha, start superscript, is less than, t, comma, t, ’, is greater than, end superscript to be generally larger for values of a<t’>a^{<t’>}a<t’>a, start superscript, is less than, t, ’, is greater than, end superscript that are highly relevant to the value the network should output for y<t’>y^{<t’>}y<t’>y, start superscript, is less than, t, ’, is greater than, end superscript. (**Note the indices in the superscripts**.)
- [ ] α<t,t’>\alpha^{<t,t’>}α<t,t’>alpha, start superscript, is less than, t, comma, t, ’, is greater than, end superscript is equal to the amount of attention y<t>y^{<t>}y<t>y, start superscript, is less than, t, is greater than, end superscript should pay to a<t’>a^{<t’>}a<t’>a, start superscript, is less than, t, ’, is greater than, end superscript

## Question 7 (MultipleChoiceQuestion)

The network learns where to “pay attention” by learning the values e<t,t’>e^{<t,t’>}e<t,t’>e, start superscript, is less than, t, comma, t, ’, is greater than, end superscript, which are computed using a small neural network:

We can't replace s<t−1>s^{<t-1>}s<t−1>s, start superscript, is less than, t, minus, 1, is greater than, end superscript with s<t> s^{<t>}s<t>s, start superscript, is less than, t, is greater than, end superscript as an input to this neural network. This is because s<t>s^{<t>}s<t>s, start superscript, is less than, t, is greater than, end superscript depends on α<t,t’>\alpha^{<t,t’>}α<t,t’>alpha, start superscript, is less than, t, comma, t, ’, is greater than, end superscript which in turn depends on e<t,t’>e^{<t,t’>}e<t,t’>e, start superscript, is less than, t, comma, t, ’, is greater than, end superscript; so at the time we need to evaluate this network, we haven’t computed s<t>s^{<t>}s<t>s, start superscript, is less than, t, is greater than, end superscript yet.

- [ ] False
- [ ] True

## Question 8 (MultipleChoiceQuestion)

The attention mechanism was primarily introduced to solve the information bottleneck problem in standard encoder-decoder models. In which situation is this mechanism **less critical** for achieving good performance?

- [ ] The input sequence length TxT\_xTx​T, start subscript, x, end subscript is large.
- [ ] The input sequence length TxT\_xTx​T, start subscript, x, end subscript is small.

## Question 9 (MultipleChoiceQuestion)

Under the CTC model, identical repeated characters not separated by the “blank” character (\_) are collapsed. Under the CTC model, what does the following string collapse to?

\_\_c\_oo\_o\_kk\_\_\_b\_ooooo\_\_oo\_\_kkk

- [ ] coookkboooooookkk
- [ ] cookbook
- [ ] cook book
- [ ] cokbok

## Question 10 (MultipleChoiceQuestion)

In trigger word detection, x<t>x^{<t>}x<t>x, start superscript, is less than, t, is greater than, end superscript is:

- [ ] Whether someone has just finished saying the trigger word at time tttt.
- [ ] Whether the trigger word is being said at time tttt.
- [ ] The tttt-th input word, represented as either a one-hot vector or a word embedding.
- [ ] Features of the audio (such as spectrogram features) at time tttt.

