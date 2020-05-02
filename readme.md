# Fisherfaces examples

This library is Bytefish's Fisherfaces library for image classification. I downloaded it and played around a little bit to learn how to use it. It's pure MATLAB/Octave code only. 

I decide to make a conclusion what would work with Fisherfaces. Normally, today deep neural networks with convolutional neural networks(CNN) are often used. But they have their pros and cons. The prons with deep neural network is that they can handle large and complex different amout of data. The cons is that training a deep neural network requires time and patience and lots of data. Deep neural network is nothing you train over a half an hour and expecting it would fit all the nonlinearities.

So I picked up servral image databases that are avaiable for free, but under some few circumstances. The can not be used for commersial use, only research use. So here is my research about the result from Fisherfaces method.

# Databases
I have selected

- FEI Face Database
- IMPA-FACE3D Database
- JAFFED Database
- Yale Database

And then I have train a Fisherfaces model and check its validation.

The FEI Face database constains two types of classes. People who smiles and people who don't smile.
![a](https://raw.githubusercontent.com/DanielMartensson/FisherFaces-Examples/master/pictures/FEI%20Face%20Database%20sample/5a.jpg)

![a](https://raw.githubusercontent.com/DanielMartensson/FisherFaces-Examples/master/pictures/FEI%20Face%20Database%20sample/5b.jpg)

The IMPA-FACE3D database contains different face expressions with few images of different camera angles.
The JAFFED Database contains different face expressions of japanese women.
Yale Database contains different face expressions with few images of different lightning onto the face.

It's very few images in every database and that's the point by using Fisherfaces.

# Validation


| Database\Method                         | Fisherfaces            | Eigenfaces  | Shape                                                      |
| ---------------------------------------:|-----------------------:| ------------:| ----------------------------------------------------------:|
| IMPA-FACE3D                             | 74.17%                 | 74.44%       | Different face expressions + few different camera angles   |
| Yale Database                           | 98.00%                 | 78.00%       | Different face expressions + few different lightning images| 
| Jaffed Database                         | 100.00%                | 99.00%       | Different face expressions                                 |
| FEI Face Database                       | 93.00%                 | 11.00%       | Smile and neural face only                                 |
| IMPA-FACE3D – No different camera angles| 93.33%                 | 90.83%       | Different face expressions and removed the camera angles   |

# Conclusion

Two methods has been used. Fisher Faces and Eigenfaces. Fisherfaces is just an extension to Eigenfaces and here we can see
that Fisherfaces wins over Eigenfaces, except IMPA-FACE3D library. But that's not fair because IMPA-FACE3D had few images where the camera took pictures behind the head.

So my conclusions to this simulation are that:

- Fisherfaces is better choice than Eigenfaces
- Fisherfaces can do classification with small amout of data. E.g 11 pictures of 15 people.
- Fisherfaces can handle different lightning onto the face
- Fisherfaces can handle two classes where two classes contains different people. Eigenfaces cannot.
- Fisherfaces can handle noisy background


