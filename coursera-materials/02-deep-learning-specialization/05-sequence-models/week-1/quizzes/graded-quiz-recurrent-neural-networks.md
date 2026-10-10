---
type: graded-quiz
specialization: Deep Learning Specialization
course: Sequence Models
week: 1
section: Quiz
item_title: Recurrent Neural Networks  
source_url: https://www.coursera.org/learn/nlp-sequence-models/assignment-submission/OwTDf/recurrent-neural-networks
language: en
extracted_at: 2026-10-08T22:59:23+08:00
grade: 90%
status: success
---
# Recurrent Neural Networks  

**Grade: 90%**

## Question 1 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again The parentheses represent the training example and the brackets represent the word. You should choose the training example and then the word.

Suppose your training examples are sentences (sequences of words). Which of the following refers to the jthj^{th}jthj, start superscript, t, h, end superscript word in the ithi^{th}ithi, start superscript, t, h, end superscript training example?

- [ ] x(i)x^{(i)}x(i)x, start superscript, left parenthesis, i, right parenthesis, is less than, j, is greater than, end superscript
- [ ] x*(j)x^{*(j)}x*(j)x, start superscript, is less than, i, is greater than, left parenthesis, j, right parenthesis, end superscript***
- [x] x(j)*x^{(j)*}x(j)*x, start superscript, left parenthesis, j, right parenthesis, is less than, i, is greater than, end superscript***
- [ ] x(i)x^{(i)}x(i)x, start superscript, is less than, j, is greater than, left parenthesis, i, right parenthesis, end superscript

*Points: 0 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work It is appropriate when every input should have an output.

Consider this RNN:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/8b615567-f4f0-4ab1-8f99-bea1131c79fb_5ceb219e94744536886476c37c61c8ee_74a6022a-041d-4f7e-b758-43d35c9674bcimage2.png?expiry=1791557911211&hmac=rW4utdSvzHr_25wyOdfrOG66E7bWhiVCCyituwEO-js)

This specific type of architecture is appropriate when:

- [x] Tx=TyT\_x = T\_yTx​=Ty​T, start subscript, x, end subscript, equals, T, start subscript, y, end subscript
- [ ] Tx
- [ ] Tx>TyT\_x > T\_yTx​>Ty​T, start subscript, x, end subscript, is greater than, T, start subscript, y, end subscript
- [ ] Tx=1T\_x = 1Tx​=1T, start subscript, x, end subscript, equals, 1

*Points: 1 / 1*

## Question 3 (GradedCheckboxQuestion)

To which of these tasks would you apply a many-to-one RNN architecture?

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/8003e717-8e37-4ece-985c-2dc9ec8d11ab_42f81fd563234fda93f41c0484768255_74a6022a-041d-4f7e-b758-43d35c9674bcimage4.png?expiry=1791557911231&hmac=z9BtfIgh0Mtch_25AQbDsmsw_QbQUJCUnvniftCkOqM)

- [x] Image classification (input an image and output a label)
  > Feedback: This should not be selected This is an example of one-to-one architecture.
- [ ] Music genre recognition
- [ ] Language recognition from speech (input an audio clip and output a label indicating the language being spoken)
- [ ] Speech recognition (input an audio clip and output a transcript)

*Points: 0.3 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes, in a language model we try to predict the next step based on the knowledge of all prior steps.

You are training this RNN language model.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/99a1ebcf-f6be-4dd5-a10f-9abd280dcdb3_a8dc13c9a7c04c9f9b57afa1b09183bd_74a6022a-041d-4f7e-b758-43d35c9674bcimage6.png?expiry=1791557911248&hmac=qv7TQPjjOFdiU22hV8VmrenYWVAi9WKqpA5k1Qn4MJk)

At the ttht^{th}ttht, start superscript, t, h, end superscript time step, what is the RNN doing?

- [ ] Estimating P(y<1>,y<2>,…,y)P(y^{<1>}, y^{<2>}, …, y^{})P(y<1>,y<2>,…,y)P, left parenthesis, y, start superscript, is less than, 1, is greater than, end superscript, comma, y, start superscript, is less than, 2, is greater than, end superscript, comma, …, comma, y, start superscript, is less than, t, minus, 1, is greater than, end superscript, right parenthesis
- [ ] Estimating P(y)P(y^{})P(y)P, left parenthesis, y, start superscript, is less than, t, is greater than, end superscript, right parenthesis
- [x] Estimating P(y∣y<1>,y<2>,…,y)P(y^{} \mid y^{<1>}, y^{<2>}, …, y^{})P(y∣y<1>,y<2>,…,y)P, left parenthesis, y, start superscript, is less than, t, is greater than, end superscript, \mid, y, start superscript, is less than, 1, is greater than, end superscript, comma, y, start superscript, is less than, 2, is greater than, end superscript, comma, …, comma, y, start superscript, is less than, t, minus, 1, is greater than, end superscript, right parenthesis
- [ ] Estimating P(y∣y<1>,y<2>,…,y)P(y^{} \mid y^{<1>}, y^{<2>}, …, y^{})P(y∣y<1>,y<2>,…,y)P, left parenthesis, y, start superscript, is less than, t, is greater than, end superscript, \mid, y, start superscript, is less than, 1, is greater than, end superscript, comma, y, start superscript, is less than, 2, is greater than, end superscript, comma, …, comma, y, start superscript, is less than, t, is greater than, end superscript, right parenthesis

*Points: 1 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again No, the probabilities output by the RNN are not used to pick the highest probability word and the ground-truth word from the training set is not the input to the next time-step.

You have finished training a language model RNN and are using it to sample random sentences, as follows:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/b76545c5-8f42-4149-b766-7f32b2e3579d_ede80b704dab423e961d7ade5be3c0ff_74a6022a-041d-4f7e-b758-43d35c9674bcimage8.png?expiry=1791557911287&hmac=NUUfRT-DROAqeasvcACfNLsrt3Cd_4PgEvWp1bkl7N8)

True/False: In this sample sentence, step t uses the probabilities output by the RNN to pick the highest probability word for that time-step. Then it passes the ground-truth word from the training set to the next time-step.

- [x] True
- [ ] False

*Points: 0 / 1*

## Question 6 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work

You are training an RNN model, and find that your weights and activations are all taking on the value of NaN (“Not a Number”). Which of these is the most likely cause of this problem?

- [ ] Vanishing gradient problem.
- [x] Exploding gradient problem.
- [ ] The model used the ReLU activation function to compute g(z), where z is too large.
- [ ] The model used the Sigmoid activation function to compute g(z), where z is too large.

*Points: 1 / 1*

## Question 7 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Correct, Γ 𝑢 Γ u ​ \Gamma, start subscript, u, end subscript is a vector of dimension equal to the number of hidden units in the LSTM.

Suppose you are training an LSTM. You have a 10000 word vocabulary, and are using an LSTM with 100-dimensional activations a<t>a^{<t>}a<t>a, start superscript, is less than, t, is greater than, end superscript. What is the dimension of Γu\Gamma\_uΓu​\Gamma, start subscript, u, end subscript at each time step?

- [ ] 1
- [x] 100
- [ ] 300
- [ ] 10000

*Points: 1 / 1*

## Question 8 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes. You should not remove the update gate. The update gate defines whether the memory is refreshed or kept; without it, the model cannot control its memory state. The standard simplification for a GRU involves removing the relevance gate ( Γ 𝑟 Γ r ​ \Gamma, start subscript, r, end subscript ), which simplifies the candidate calculation but leaves the memory-retention mechanism intact.

**True/False**: To simplify the GRU architecture while maintaining its ability to handle vanishing gradients and long-term dependencies, you should remove the update gate (Γu\Gamma\_uΓu​\Gamma, start subscript, u, end subscript) and set Γu=0\Gamma\_u = 0Γu​=0\Gamma, start subscript, u, end subscript, equals, 0.

- [x] False
- [ ] True

*Points: 1 / 1*

## Question 9 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again No, the GRU's Γ 𝑟 Γ r ​ \Gamma, start subscript, r, end subscript plays a different role than the LSTM's Γ 𝑓 Γ f ​ \Gamma, start subscript, f, end subscript and Γ 𝑢 Γ u ​ \Gamma, start subscript, u, end subscript .

Here are the equations for the GRU and the LSTM:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/c6bf1573-4aff-4c20-b915-4e03e97ddc95_89b211d716a54a3da7cb67a68af32263_74a6022a-041d-4f7e-b758-43d35c9674bcimage11.png?expiry=1791557911304&hmac=xn1GxjDR5cR2q8v9eDjeS2NWT4TkREGDyXgMans9xAA)

From these, we can see that the Update Gate and Forget Gate in the LSTM play a role similar to \_\_\_\_\_\_\_ and \_\_\_\_\_\_ in the GRU. What should go in the blanks?

- [ ] Γu\Gamma\_uΓu​\Gamma, start subscript, u, end subscript and 1−Γu1-\Gamma\_u1−Γu​1, minus, \Gamma, start subscript, u, end subscript
- [x] Γu\Gamma\_uΓu​\Gamma, start subscript, u, end subscript and Γr\Gamma\_rΓr​\Gamma, start subscript, r, end subscript
- [ ] 1−Γu1-\Gamma\_u1−Γu​1, minus, \Gamma, start subscript, u, end subscript and Γu\Gamma\_uΓu​\Gamma, start subscript, u, end subscript
- [ ] Γr\Gamma\_rΓr​\Gamma, start subscript, r, end subscript and Γu\Gamma\_uΓu​\Gamma, start subscript, u, end subscript

*Points: 0 / 1*

## Question 10 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work

Your mood is heavily dependent on the current and past few days’ weather. You’ve collected data for the past 365 days on the weather, which you represent as a sequence as x<1>,…,x<365>x^{<1>}, …, x^{<365>}x<1>,…,x<365>x, start superscript, is less than, 1, is greater than, end superscript, comma, …, comma, x, start superscript, is less than, 365, is greater than, end superscript. You’ve also collected data on your mood, which you represent as y<1>,…,y<365>y^{<1>}, …, y^{<365>}y<1>,…,y<365>y, start superscript, is less than, 1, is greater than, end superscript, comma, …, comma, y, start superscript, is less than, 365, is greater than, end superscript. You’d like to build a model to map from *x*→*y*. Should you use a Unidirectional RNN or Bidirectional RNN for this problem?

- [ ] Bidirectional RNN, because this allows backpropagation to compute more accurate gradients.
- [ ] Unidirectional RNN, because the value of yy^{}yy, start superscript, is less than, t, is greater than, end superscript depends only on xx^{}xx, start superscript, is less than, t, is greater than, end superscript, and not other days’ weather.
- [x] Unidirectional RNN, because the value of yy^{}yy, start superscript, is less than, t, is greater than, end superscript depends only on x<1>,…,xx^{<1>}, …, x^{}x<1>,…,xx, start superscript, is less than, 1, is greater than, end superscript, comma, …, comma, x, start superscript, is less than, t, is greater than, end superscript, but not on x<1>,…,x<365>x^{<1>}, …, x^{<365>}x<1>,…,x<365>x, start superscript, is less than, 1, is greater than, end superscript, comma, …, comma, x, start superscript, is less than, 365, is greater than, end superscript.
- [ ] Bidirectional RNN, because this allows the prediction of mood on day t to take into account more information.

*Points: 1 / 1*

