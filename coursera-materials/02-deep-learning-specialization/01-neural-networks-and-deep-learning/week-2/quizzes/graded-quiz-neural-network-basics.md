---
type: graded-quiz
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Quiz
item_title: Neural Network Basics               
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/assignment-submission/c1bic/neural-network-basics
language: en
extracted_at: 2026-10-08T22:59:22+08:00
grade: 80%
status: success
---
# Neural Network Basics               

**Grade: 80%**

## Question 1 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again No. There is no mean applied in a neuron.

What does a neuron compute?

- [x] A neuron computes the mean of all features before applying the output to an activation function
- [ ] A neuron computes a linear function z=Wx+bz = Wx + bz=Wx+bz, equals, W, x, plus, b followed by an activation function
- [ ] A neuron computes a function g that scales the input x linearly (Wx + b)
- [ ] A neuron computes an activation function followed by a linear function z=Wx+bz = Wx + bz=Wx+bz, equals, W, x, plus, b

*Points: 0 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again No. This is the value of the 𝐿 1 L 1 ​ L, start subscript, 1, end subscript -loss.

Suppose that y^=0.5\hat{y} = 0.5y^​=0.5y, with, hat, on top, equals, 0, point, 5 and y=0y = 0y=0y, equals, 0. What is the value of the "Logistic Loss"? Choose the best option.

- [ ] L(y^,y)=−(y log⁡y^+(1−y) log⁡(1−y^)) \mathcal{L}(\hat{y}, y) = - \left( y \, \log \hat{y} + (1-y)\ \log ( 1 - \hat{y}) \right) L(y^​,y)=−(ylogy^​+(1−y) log(1−y^​))L, left parenthesis, y, with, hat, on top, comma, y, right parenthesis, equals, minus, left parenthesis, y, log, y, with, hat, on top, plus, left parenthesis, 1, minus, y, right parenthesis, space, log, left parenthesis, 1, minus, y, with, hat, on top, right parenthesis, right parenthesis
- [ ] 0.693
- [ ] +∞+\infty+∞plus, infinity
- [x] 0.5

*Points: 0 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again No. This requires that 8 = n*3 where n is an unknown size to be determined. Since n = 8/3 is not an integer, the reshape is not possible.

Suppose x is a (8, 1) array. Which of the following is a valid reshape?

- [x] x.reshape(-1, 3)
- [ ] x.reshape(1, 4, 3)
- [ ] x.reshape(2, 2, 2)
- [ ] x.reshape(2, 4, 4)

*Points: 0 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes. Broadcasting is used, so row b is copied 3 times so it can be summed to each row of a.

Consider the following random arrays aaaa and bbbb, and cccc:

a=np.random.randn(3,4)a = np.random.randn(3, 4)a=np.random.randn(3,4)a, equals, n, p, point, r, a, n, d, o, m, point, r, a, n, d, n, left parenthesis, 3, comma, 4, right parenthesis # a.shape=(3,4)a.shape = (3, 4)a.shape=(3,4)a, point, s, h, a, p, e, equals, left parenthesis, 3, comma, 4, right parenthesis

b=np.random.randn(1,4)b = np.random.randn(1, 4)b=np.random.randn(1,4)b, equals, n, p, point, r, a, n, d, o, m, point, r, a, n, d, n, left parenthesis, 1, comma, 4, right parenthesis # b.shape=(1,4) b.shape = (1, 4)b.shape=(1,4)b, point, s, h, a, p, e, equals, left parenthesis, 1, comma, 4, right parenthesis

c=a+bc = a + bc=a+bc, equals, a, plus, b

What will be the shape of cccc?

- [x] c.shape = (3, 4)
- [ ] The computation cannot happen because it is not possible to broadcast more than one dimension.
- [ ] c.shape = (1, 4)
- [ ] c.shape = (3, 1)

*Points: 1 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes. Broadcasting is invoked, so row b is multiplied element-wise with each row of a to create c.

Consider the two following random arrays aaaa and bbbb:

a=np.random.randn(4,3)a = np.random.randn(4, 3)a=np.random.randn(4,3)a, equals, n, p, point, r, a, n, d, o, m, point, r, a, n, d, n, left parenthesis, 4, comma, 3, right parenthesis # a.shape=(4,3)a.shape = (4, 3)a.shape=(4,3)a, point, s, h, a, p, e, equals, left parenthesis, 4, comma, 3, right parenthesis

b=np.random.randn(1,3)b = np.random.randn(1, 3)b=np.random.randn(1,3)b, equals, n, p, point, r, a, n, d, o, m, point, r, a, n, d, n, left parenthesis, 1, comma, 3, right parenthesis # b.shape=(1,3)b.shape = (1, 3)b.shape=(1,3)b, point, s, h, a, p, e, equals, left parenthesis, 1, comma, 3, right parenthesis

c=a∗bc = a\*bc=a∗bc, equals, a, times, b

What will be the shape of cccc?

- [x] c.shape = (4, 3)
- [ ] c.shape = (1, 3)
- [ ] The computation cannot happen because it is not possible to broadcast more than one dimension.
- [ ] The computation cannot happen because the sizes don't match.

*Points: 1 / 1*

## Question 6 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work

Suppose you have nxn\_xnx​n, start subscript, x, end subscript input features per example. Recall that X=[x(1)x(2)...x(m)]X = [x^{(1)} x^{(2)} ... x^{(m)}]X=[x(1)x(2)...x(m)]X, equals, open bracket, x, start superscript, left parenthesis, 1, right parenthesis, end superscript, x, start superscript, left parenthesis, 2, right parenthesis, end superscript, point, point, point, x, start superscript, left parenthesis, m, right parenthesis, end superscript, close bracket. What is the dimension of X?

- [ ] (m,nx)(m,n\_x)(m,nx​)left parenthesis, m, comma, n, start subscript, x, end subscript, right parenthesis
- [ ] (1,m)(1,m)(1,m)left parenthesis, 1, comma, m, right parenthesis
- [ ] (m,1)(m,1)(m,1)left parenthesis, m, comma, 1, right parenthesis
- [x] (nx,m)(n\_x, m)(nx​,m)left parenthesis, n, start subscript, x, end subscript, comma, m, right parenthesis

*Points: 1 / 1*

## Question 7 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes, recall that * indicates the element wise multiplication and that np.dot() is the matrix multiplication. Thus ( ( 2 ) ( 2 ) + ( 1 ) ( 1 ) ( 2 ) ( 1 ) + ( 1 ) ( 3 ) ( 1 ) ( 2 ) + ( 3 ) ( 1 ) ( 1 ) ( 1 ) + ( 3 ) ( 3 ) ) ( (2)(2)+(1)(1) (1)(2)+(3)(1) ​ (2)(1)+(1)(3) (1)(1)+(3)(3) ​ ) \begin{pmatrix} (2)(2) + (1)(1) & (2)(1) + (1)(3) \\ (1)(2) + (3)(1) & (1)(1) + (3)(3) \end{pmatrix} .

Consider the following array:

a=np.array([[2,1],[1,3]])a = np.array([[2, 1], [1, 3]])a=np.array([[2,1],[1,3]])a, equals, n, p, point, a, r, r, a, y, left parenthesis, open bracket, open bracket, 2, comma, 1, close bracket, comma, open bracket, 1, comma, 3, close bracket, close bracket, right parenthesis

What is the result of np.dot(a,a)np.dot(a,a)np.dot(a,a)n, p, point, d, o, t, left parenthesis, a, comma, a, right parenthesis?

- [ ] The computation cannot happen because the sizes don't match. It's going to be an "Error"!
- [ ] (4119)\begin{pmatrix} 4 & 1 \\ 1 & 9 \end{pmatrix}(41​19​)\begin{pmatrix} 4 & 1 \\ 1 & 9 \end{pmatrix}
- [x] (55510)\begin{pmatrix} 5 & 5 \\ 5 & 10 \end{pmatrix}(55​510​)\begin{pmatrix} 5 & 5 \\ 5 & 10 \end{pmatrix}
- [ ] (4226)\begin{pmatrix} 4 & 2 \\ 2 & 6 \end{pmatrix}(42​26​)\begin{pmatrix} 4 & 2 \\ 2 & 6 \end{pmatrix}

*Points: 1 / 1*

## Question 8 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again

Consider the following code snippet:

a.shape=(3,4)a.shape = (3,4)a.shape=(3,4)a, point, s, h, a, p, e, equals, left parenthesis, 3, comma, 4, right parenthesis

b.shape=(4,1)b.shape = (4,1)b.shape=(4,1)b, point, s, h, a, p, e, equals, left parenthesis, 4, comma, 1, right parenthesis

for i in range(3):

for j in range(4):

c[i][j] = a[i][j] + b[j]

How do you vectorize this?

- [ ] c = a.T + b.T
- [ ] c = a + b.T
- [x] c = a.T + b
- [ ] c = a + b

*Points: 0 / 1*

## Question 9 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes. The array b is a column vector. This is copied two times and added to the array a to construct the array c.

Consider the following arrays:

a=np.array([[1,1],[1,−1]])a = np.array([[1, 1], [1, -1]])a=np.array([[1,1],[1,−1]])a, equals, n, p, point, a, r, r, a, y, left parenthesis, open bracket, open bracket, 1, comma, 1, close bracket, comma, open bracket, 1, comma, minus, 1, close bracket, close bracket, right parenthesis

b=np.array([[2],[3]])b = np.array([[2], [3]])b=np.array([[2],[3]])b, equals, n, p, point, a, r, r, a, y, left parenthesis, open bracket, open bracket, 2, close bracket, comma, open bracket, 3, close bracket, close bracket, right parenthesis

c=a+bc = a + bc=a+bc, equals, a, plus, b

Which of the following arrays is stored in cccc?

- [x] 3342\begin{matrix} 3 & 3 \\ 4 & 2 \end{matrix}34​32​\begin{matrix} 3 & 3 \\ 4 & 2 \end{matrix}
- [ ] (33314452)\begin{pmatrix} 3 & 3 \\ 3 & 1 \\ 4 & 4 \\ 5 & 2 \end{pmatrix}⎝⎜⎜⎜⎛​3345​3142​⎠⎟⎟⎟⎞​\begin{pmatrix} 3 & 3 \\ 3 & 1 \\ 4 & 4 \\ 5 & 2 \end{pmatrix}
- [ ] 3432\begin{matrix} 3 & 4 \\ 3 & 2 \end{matrix}33​42​\begin{matrix} 3 & 4 \\ 3 & 2 \end{matrix}
- [ ] The computation cannot happen because the sizes don't match. It's going to be an "Error"!

*Points: 1 / 1*

## Question 10 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes. 𝐽 = 𝑟 + 𝑠 = 𝑢 ∗ 𝑣 + 𝑤 ∗ 𝑥 = ( 𝑎 + 𝑏 ) ∗ ( 𝑎 − 𝑏 ) + ( 𝑏 + 𝑐 ) ∗ ( 𝑏 − 𝑐 ) = 𝑎 2 − 𝑏 2 + 𝑏 2 − 𝑐 2 = 𝑎 2 − 𝑐 2 J=r+s=u∗v+w∗x=(a+b)∗(a−b)+(b+c)∗(b−c)=a 2 −b 2 +b 2 −c 2 =a 2 −c 2 J, equals, r, plus, s, equals, u, times, v, plus, w, times, x, equals, left parenthesis, a, plus, b, right parenthesis, times, left parenthesis, a, minus, b, right parenthesis, plus, left parenthesis, b, plus, c, right parenthesis, times, left parenthesis, b, minus, c, right parenthesis, equals, a, squared, minus, b, squared, plus, b, squared, minus, c, squared, equals, a, squared, minus, c, squared .

Consider the following computational graph.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/86bb3516-7980-49ee-ab1d-eeffc4064795_be8ab3852a5345b4b60f18bdeec83bdf_6757745e-eb0b-423e-b0a7-637a78d6c30eimage2.png?expiry=1791557697473&hmac=CgfCiVh5Xq3uwab6k52gIOnP-gSyKbNWV3x_xaco23Q)

What is the output of J?

- [ ] (a−b)∗(a−c)(a-b)\*(a-c)(a−b)∗(a−c)left parenthesis, a, minus, b, right parenthesis, times, left parenthesis, a, minus, c, right parenthesis
- [x] a2−c2a^2 - c^2a2−c2a, squared, minus, c, squared
- [ ] a2+b2−c2a^2 + b^2 - c^2a2+b2−c2a, squared, plus, b, squared, minus, c, squared
- [ ] a2−b2a^2 - b^2a2−b2a, squared, minus, b, squared

*Points: 1 / 1*

