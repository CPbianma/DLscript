---
type: graded-quiz
specialization: Deep Learning Specialization
course: Sequence Models
week: 2
section: Quiz
item_title: Natural Language Processing & Word Embeddings  
source_url: https://www.coursera.org/learn/nlp-sequence-models/assignment-submission/G5uWp/natural-language-processing-word-embeddings
language: en
extracted_at: 2026-10-08T22:59:23+08:00
grade: 90%
status: success
---
# Natural Language Processing & Word Embeddings  

**Grade: 90%**

## Question 1 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work No, the dimension of word vectors is usually smaller than the size of the vocabulary. Most common sizes for word vectors range between 50 and 1000.

True/False: Suppose you learn a word embedding for a vocabulary of 60000 words. Then the embedding vectors could be 60000 dimensional, so as to capture the full range of variation and meaning in those words.

- [ ] True
- [x] False

*Points: 1000.1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again t-SNE is a non-linear dimensionality reduction technique.

True/False: t-SNE is a linear transformation that allows us to solve analogies on word vectors.

- [ ] False
- [x] True

*Points: 0 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes, word vectors empower your model with an incredible ability to generalize. The vector for “ecstatic” would contain a positive/happy connotation which will probably make your model classify the sentence as a "1".

Suppose you download a pre-trained word embedding which has been trained on a huge corpus of text. You then use this word embedding to train an RNN for a language task of recognizing if someone is happy from a short snippet of text, using a small training set.

|  |  |
| --- | --- |
| **x (input text)** | **y (happy?)** |
| I'm feeling wonderful today! | 1 |
| I'm bummed my cat is ill. | 0 |
| Really enjoying this! | 1 |

Then even if the word “ecstatic” does not appear in your small training set, your RNN might reasonably be expected to recognize “I’m ecstatic” as deserving a label y=1y = 1y=1y, equals, 1.

- [x] True
- [ ] False

*Points: 1 / 1*

## Question 4 (GradedCheckboxQuestion)

Which of these equations do you think should hold for a good word embedding? (Check all that apply)

- [x] eman−eking≈ewoman−equeene\_{man} - e\_{king} \approx e\_{woman} - e\_{queen}eman​−eking​≈ewoman​−equeen​e, start subscript, m, a, n, end subscript, minus, e, start subscript, k, i, n, g, end subscript, approximately equals, e, start subscript, w, o, m, a, n, end subscript, minus, e, start subscript, q, u, e, e, n, end subscript ✅correct
  > Feedback: Nice work The order of words is correct in this analogy.
- [x] eman−ewoman≈eking−equeene\_{man} - e\_{woman} \approx e\_{king} - e\_{queen}eman​−ewoman​≈eking​−equeen​e, start subscript, m, a, n, end subscript, minus, e, start subscript, w, o, m, a, n, end subscript, approximately equals, e, start subscript, k, i, n, g, end subscript, minus, e, start subscript, q, u, e, e, n, end subscript ✅correct
  > Feedback: Nice work The order of words is correct in this analogy.
- [ ] eman−ewoman≈equeen−ekinge\_{man} - e\_{woman} \approx e\_{queen} - e\_{king}eman​−ewoman​≈equeen​−eking​e, start subscript, m, a, n, end subscript, minus, e, start subscript, w, o, m, a, n, end subscript, approximately equals, e, start subscript, q, u, e, e, n, end subscript, minus, e, start subscript, k, i, n, g, end subscript
- [ ] eman−eking≈equeen−ewomane\_{man} - e\_{king} \approx e\_{queen} - e\_{woman}eman​−eking​≈equeen​−ewoman​e, start subscript, m, a, n, end subscript, minus, e, start subscript, k, i, n, g, end subscript, approximately equals, e, start subscript, q, u, e, e, n, end subscript, minus, e, start subscript, w, o, m, a, n, end subscript

*Points: 1 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes, the element-wise multiplication will be extremely inefficient.

Let AAAA be an embedding matrix, and let o4567o\_{4567}o4567​o, start subscript, 4567, end subscript be a one-hot vector corresponding to word 4567. Then to get the embedding of word 4567, why don’t we call A∗o4567A \* o\_{4567}A∗o4567​A, times, o, start subscript, 4567, end subscript in Python?

- [x] It is computationally wasteful.
- [ ] This doesn’t handle unknown words ().
- [ ] The correct formula is AT∗o4567A^T \* o\_{4567}AT∗o4567​A, start superscript, T, end superscript, times, o, start subscript, 4567, end subscript.
- [ ] None of the answers are correct: calling the Python snippet as described above is fine.

*Points: 1 / 1*

## Question 6 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Word embeddings are learned by picking a given word and trying to predict its surrounding words or vice versa.

When learning word embeddings, we pick a given word and try to predict its surrounding words or vice versa.

- [x] True
- [ ] False

*Points: 1 / 1*

## Question 7 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work

In the word2vec algorithm, you estimate P(t∣c)P(t \mid c)P(t∣c)P, left parenthesis, t, \mid, c, right parenthesis, where tttt is the target word and cccc is a context word. How are tttt and cccc chosen from the training set? Pick the best answer.

- [ ] cccc is the one word that comes immediately before tttt.
- [ ] cccc is a sequence of several words immediately before tttt.
- [ ] cccc is the sequence of all the words in the sentence before tttt.
- [x] cccc and tttt are chosen to be nearby words.

*Points: 1 / 1*

## Question 8 (GradedCheckboxQuestion)

Suppose you have a 10000 word vocabulary, and are learning 100-dimensional word embeddings. The word2vec model uses the following softmax function:

P(t ∣ c)=eθtTeC∑t′=110000eθtTeCP(t \, | \, c) = \frac{e^{\theta\_t^T e\_C}}{\sum\_{t'=1}^{10000} e^{\theta\_t^T e\_C}}P(t∣c)=∑t′=110000​eθtT​eC​eθtT​eC​​P, left parenthesis, t, vertical bar, c, right parenthesis, equals, start fraction, e, start superscript, theta, start subscript, t, end subscript, start superscript, T, end superscript, e, start subscript, C, end subscript, end superscript, divided by, sum, start subscript, t, prime, equals, 1, end subscript, start superscript, 10000, end superscript, e, start superscript, theta, start subscript, t, end subscript, start superscript, T, end superscript, e, start subscript, C, end subscript, end superscript, end fraction

Which of these statements are correct? Check all that apply.

- [ ] θt\theta\_tθt​theta, start subscript, t, end subscript and ece\_cec​e, start subscript, c, end subscript are both 10000 dimensional vectors.
- [x] θt\theta\_tθt​theta, start subscript, t, end subscript and ece\_cec​e, start subscript, c, end subscript are both trained with an optimization algorithm. ✅correct
  > Feedback: Nice work To review this concept watch the Word2Vec lecture.
- [ ] After training, we should expect θt\theta\_tθt​theta, start subscript, t, end subscript to be very close to ece\_cec​e, start subscript, c, end subscript when*t*and *c* are the same word.
- [x] θt\theta\_tθt​theta, start subscript, t, end subscript and ece\_cec​e, start subscript, c, end subscript are both 100 dimensional vectors. Feedback: To review this concept watch the *Word2Vec* lecture. ✅correct
  > Feedback: Nice work

*Points: 1 / 1*

## Question 9 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work 𝑋 𝑖 𝑗 X ij ​ X, start subscript, i, j, end subscript is the number of times word j appears in the context of word i.

Suppose you have a 10000 word vocabulary, and are learning 500-dimensional word embeddings. The GloVe model minimizes this objective:

min⁡∑i=110,000∑j=110,000f(Xij)(θiTej+bi+bj’−logXij)2\min \sum\_{i=1}^{10,000} \sum\_{j=1}^{10,000} f(X\_{ij}) (\theta\_i^T e\_j + b\_i + b\_j’ - log X\_{ij})^2min∑i=110,000​∑j=110,000​f(Xij​)(θiT​ej​+bi​+bj​’−logXij​)2\min, sum, start subscript, i, equals, 1, end subscript, start superscript, 10, comma, 000, end superscript, sum, start subscript, j, equals, 1, end subscript, start superscript, 10, comma, 000, end superscript, f, left parenthesis, X, start subscript, i, j, end subscript, right parenthesis, left parenthesis, theta, start subscript, i, end subscript, start superscript, T, end superscript, e, start subscript, j, end subscript, plus, b, start subscript, i, end subscript, plus, b, start subscript, j, end subscript, ’, minus, l, o, g, X, start subscript, i, j, end subscript, right parenthesis, squared

True/False: XijX\_{ij}Xij​X, start subscript, i, j, end subscript is the number of times word j appears in the context of word i.

- [ ] False
- [x] True

*Points: 1 / 1*

## Question 10 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work 𝑠 1 s 1 ​ s, start subscript, 1, end subscript should transfer to 𝑠 2 s 2 ​ s, start subscript, 2, end subscript

You have trained word embeddings using a text dataset of s1s\_1s1​s, start subscript, 1, end subscript words. You are considering using these word embeddings for a language task, for which you have a separate labeled dataset of s2s\_2s2​s, start subscript, 2, end subscript words. Keeping in mind that using word embeddings is a form of transfer learning, under which of these circumstances would you expect the word embeddings to be helpful?

- [x] s1s\_1s1​s, start subscript, 1, end subscript >> s2s\_2s2​s, start subscript, 2, end subscript
- [ ] s1s\_1s1​s, start subscript, 1, end subscript << s2s\_2s2​s, start subscript, 2, end subscript

*Points: 1 / 1*

