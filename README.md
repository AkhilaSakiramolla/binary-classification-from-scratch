# binary-classification-from-scratch
Implementation of binary classification of algorithm from scratch.

Problem statement:

Consider the binary classification problem of mapping a given input to two classes. Let X = Rd and Y =-1,+1 be the input space and output space, respectively. In simple words, it means that the input has d features and all of them are real valued, whereas the output can only take values -1,+1. This is one of the most common problems in machine learning and many sophisticated methods exist to solve it.

• In the question, we will solve it using the concepts we have already learned in class. Let us assume the two sets of points can be separated using a straight line i.e. the samples are linearly separable. So if d = 2, one should be able to draw a line to distinguish between the two classes. All points lying on side of the line should belong to a particular class (say 1) and the points lying on the other side should belong to another class (say 2). To see what this would look like, your first task is as follows:

Write a function that will randomly generate a dataset for this problem. Your function should randomly choose a line l, which can be denoted as ax + by + c = 0 and the line divides the plane into two sides. On one side, ax + by + c > 0 while on the other ax + by + c < 0. Use this fact to randomly generate k0 points on the side of class 0 (i.e. y = −1 ) and k1 points on the side of class 1 (i.e. y = 1). Create a plot of this dataset where all the points corresponding to one class are blue and those of the other class are green, the line dividing both classes should be red. Axes should be labeled.Note: Do not confuse the x and y in the equation of line ax + by + c = 0 with X and Y . Instead imagine these x and y as the 2D coordinate system on which you have different points which should lie on 2 sides of the line ax + by + c = 0. For example, there is a point (2, 3) in the 2D system where x = 2 and y = 3.

• If Y is the variable you are trying to predict using a feature X then in a typical Machine Learning
problem, you are tasked with a target function f which maps X to Y i.e. Find f such that Y = f(X).
When you are given a dataset for which you do not have access the target function f, you have to
learn it from the data. In this problem, we are going to learn the parameters of the line that separates
the two classes for the dataset that we constructed in problem above. As we previously mentioned,
that line can be represented as ax + by + c = 0.
The goal here is to correctly find out the coefficients a, b, and c, represented below as w which is a
vector. The algorithm to find it is a simple iterative process:
– Randomly choose a w to begin with.
– Keep on adjusting the value of w as follows until all data samples are correctly classified:
∗ Randomly choose a sample from the dataset without replacement and see if it is correctly
classified. If yes, move on to another sample.
∗ If not, then update the weights as wt+1 = wt + yx and go back to the previous step (of
randomly choosing a sample)
· wt+1 is value of w at iteration t + 1
· wt+1 is value of w at iteration t
· y is the class label for the sample under consideration
· x is the data-point under consideration
Write a function that implements this learning algorithm. The input to the function is going to be a
dataset represented by the input variable X and the target variable Y . The output of the function
should be the chosen w.
