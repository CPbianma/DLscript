---
type: graded-quiz
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Quiz
item_title: Detection Algorithms    
source_url: https://www.coursera.org/learn/convolutional-neural-networks/assignment-submission/hD0qO/detection-algorithms
language: en
extracted_at: 2026-10-08T22:52:07+08:00
grade: 100%
status: success
---
# Detection Algorithms    

**Grade: 100%**

## Question 1 (GradedMultipleChoiceQuestion)

You are building a 3-class object classification and localization algorithm. The classes are: pedestrian (c=1), car (c=2), motorcycle (c=3). What should yyyy be for the image below? Remember that “?” means “don’t care”, which means that the neural network loss function won’t care what the neural network gives for that component of the output. Recall y=[pc,bx,by,bh,bw,c1,c2,c3]y = [p\_c, b\_x, b\_y, b\_h, b\_w, c\_1, c\_2, c\_3]y=[pc​,bx​,by​,bh​,bw​,c1​,c2​,c3​]y, equals, open bracket, p, start subscript, c, end subscript, comma, b, start subscript, x, end subscript, comma, b, start subscript, y, end subscript, comma, b, start subscript, h, end subscript, comma, b, start subscript, w, end subscript, comma, c, start subscript, 1, end subscript, comma, c, start subscript, 2, end subscript, comma, c, start subscript, 3, end subscript, close bracket.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/865e120a-0d8d-48d0-ae42-0dd57b7bbeae_b679e6c96d6c4f05a0e6ae2eae433ddb_25f2144e-1e69-47f5-b930-9f9e1d745eefimage1.png?expiry=1791557274698&hmac=GfrGIVzf0TKIJVe0CZnmCr7pFpDt7hLI5TmH9x-RFhI)

- [ ] y=[1,?,?,?,?,?,?,?]y = [1, ?, ?, ?, ?, ?, ?, ?]y=[1,?,?,?,?,?,?,?]y, equals, open bracket, 1, comma, question mark, comma, question mark, comma, question mark, comma, question mark, comma, question mark, comma, question mark, comma, question mark, close bracket
- [ ] y=[?,?,?,?,?,?,?,?]y = [?, ?, ?, ?, ?, ?, ?, ?]y=[?,?,?,?,?,?,?,?]y, equals, open bracket, question mark, comma, question mark, comma, question mark, comma, question mark, comma, question mark, comma, question mark, comma, question mark, comma, question mark, close bracket
- [ ] y=[1,?,?,?,?,0,0,0]y = [1, ?, ?, ?, ?, 0, 0, 0]y=[1,?,?,?,?,0,0,0]y, equals, open bracket, 1, comma, question mark, comma, question mark, comma, question mark, comma, question mark, comma, 0, comma, 0, comma, 0, close bracket
- [x] y=[0,?,?,?,?,?,?,?]y = [0, ?, ?, ?, ?, ?, ?, ?]y=[0,?,?,?,?,?,?,?]y, equals, open bracket, 0, comma, question mark, comma, question mark, comma, question mark, comma, question mark, comma, question mark, comma, question mark, comma, question mark, close bracket

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

You are working on a factory automation task. Your system will see a can of soft-drink coming down a conveyor belt, and you want it to take a picture and decide whether (i) there is a soft-drink can in the image, and if so (ii) its bounding box. Since the soft-drink can is round, the bounding box is always square, and the soft-drink can always appear the same size in the image. There is at most one soft-drink can in each image. Here are some typical images in your training set:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/77a0622e-65ab-44b2-9df4-94ac30f1137d_8d18fd2edf9f49bb8948d951a153ffca_25f2144e-1e69-47f5-b930-9f9e1d745eefimage4.png?expiry=1791557274717&hmac=iebEAmWBpRBDvMWSx3avwoxeMtfMsD6rzCUba_mmtqA)

The most adequate output for a network to do the required task is y=[pc,bx,by,bh,bw,c1]y = [p\_c, b\_x, b\_y, b\_h, b\_w, c\_1]y=[pc​,bx​,by​,bh​,bw​,c1​]y, equals, open bracket, p, start subscript, c, end subscript, comma, b, start subscript, x, end subscript, comma, b, start subscript, y, end subscript, comma, b, start subscript, h, end subscript, comma, b, start subscript, w, end subscript, comma, c, start subscript, 1, end subscript, close bracket. (Which of the following do you agree with the most?)

- [ ] True, since this is a localization problem.
- [ ] False, since we only need two values c1c\_1c1​c, start subscript, 1, end subscript for no soft-drink can and c2c\_2c2​c, start subscript, 2, end subscript for soft-drink can.
- [x] False, we don't need bhb\_hbh​b, start subscript, h, end subscript, bwb\_wbw​b, start subscript, w, end subscript since the cans are all the same size.
- [ ] True, pcp\_cpc​p, start subscript, c, end subscript indicates the presence of an object of interest, bx,by,bh,bwb\_x, b\_y, b\_h, b\_wbx​,by​,bh​,bw​b, start subscript, x, end subscript, comma, b, start subscript, y, end subscript, comma, b, start subscript, h, end subscript, comma, b, start subscript, w, end subscript indicate the position of the object and its bounding box, and c1c\_1c1​c, start subscript, 1, end subscript indicates the probability of there being a can of soft-drink.

*Points: 1 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

When building a neural network that inputs a picture of a person's face and outputs N landmarks on the face (assume that the input image contains exactly one face), we need two coordinates for each landmark, thus we need 2N output units. True/False?

- [x] True
- [ ] False

*Points: 1 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

When training one of the object detection systems described in the lectures, each image must have zero or exactly one bounding box. True/False?

- [ ] True
- [x] False

*Points: 1 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

What is the IoU between these two boxes? The upper-left box is 2x2, and the lower-right box is 2x3. The overlapping region is 1x1.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/99019960-84f5-4496-90ab-10c6c2201955_46fa70a8a55045ccbf6b9fd4794bf471_25f2144e-1e69-47f5-b930-9f9e1d745eefimage6.png?expiry=1791557274735&hmac=RuSjMyJF0-qJYHGqBvQKqQTcfe5qyJVIn9FMhYPM_xw)

- [x] 1/9
- [ ] None of the above
- [ ] ⅙
- [ ] 1/10

*Points: 9.1 / 1*

## Question 6 (GradedMultipleChoiceQuestion)

Suppose you run non-max suppression on the predicted boxes nelow. The parameters you use for non-max suppression are that boxes with probability ≤0.7\leq 0.7≤0.7is less than or equal to, 0, point, 7 are discarded, and the IoU threshold for deciding if two boxes overlap is 0.50.50.50, point, 5.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/7472d899-b0c9-4ef9-8230-43d4ff524493_f5981570b1c14d5ebb0d717d5624a4fe_25f2144e-1e69-47f5-b930-9f9e1d745eefimage8.png?expiry=1791557274753&hmac=W3ANadXcAUBEDSdJmFB3GbZy0eGMpNKjA4-ZBQvdCsU)

After non-max suppression, only three boxes remain. True/False?

- [x] True
- [ ] False

*Points: 1 / 1*

## Question 7 (GradedMultipleChoiceQuestion)

Suppose you are using YOLO on a 19x19 grid, on a detection problem with 20 classes, and with 5 anchor boxes. During training, for each image you will need to construct an output volume yyyy as the target value for the neural network; this corresponds to the last layer of the neural network. (yyyy may include some “?”, or “don’t cares”). What is the dimension of this output volume?

- [x] 19x19x(5x25)
- [ ] 19x19x(5x20)
- [ ] 19x19x(25x20)
- [ ] 19x19x(20x25)

*Points: 1 / 1*

## Question 8 (GradedMultipleChoiceQuestion)

We are trying to build a system that assigns a value of 1 to each pixel that is part of a tumor from a medical image taken from a patient.

This is a problem of localization? True/False

- [x] False
- [ ] True

*Points: 1 / 1*

## Question 9 (GradedMultipleChoiceQuestion)

Using the concept of Transpose Convolution, fill in the values of **X**, **Y** and **Z** below.

(*padding = 1, stride = 2*)

**Input****: 2x2**

|  |  |
| --- | --- |
| 1 | 2 |
| 3 | 4 |

**Filter****: 3x3**

|  |  |  |
| --- | --- | --- |
| 1 | 0 | -1 |
| 1 | 0 | -1 |
| 1 | 0 | -1 |

**Result****: 6x6**

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |
|  | 0 | 1 | 0 | -2 |  |
|  | 0 | **X** | 0 | **Y** |  |
|  | 0 | 1 | 0 | **Z** |  |
|  | 0 | 1 | 0 | -4 |  |
|  |  |  |  |  |  |

- [ ] X = -2, Y = -6, Z = -4
- [ ] X = 2, Y = -6, Z = 4
- [ ] X = 2, Y = 6, Z = 4
- [x] X = 2, Y = -6, Z = -4

*Points: 1 / 1*

## Question 10 (GradedMultipleChoiceQuestion)

Suppose your input to a U-Net architecture is hhhh x wwww x 3333, where 3 denotes your number of channels (RGB). What will be the dimension of your output ?

- [ ] hhhh x wwww x nnnn, where n = number of filters used in the algorithm
- [ ] hhhh x wwww x nnnn, where n = number of of output channels
- [ ] hhhh x wwww x nnnn, where n = number of input channels
- [x] hhhh x wwww x nnnn, where n = number of output classes

*Points: 1 / 1*

