
# Cross-entropy: an exiting concept and its application in reducing loss. 

In image classifications, what we want is for the network model to predict correct images of dogs, cats, etc...

Let's say we a set of images in 3 classes of animals: dogs, cats, birds. In form of hot-encoding vectors and for the ease 
of training a network, dog class can be represented as a vector of [1,0,0]; cat is [0,1,0]; bird is [0,0,1]. The ideal model
will predict a test images belong to one of these classes. However, the reality is not. For a given test image, a model 
can predict it as [0.6, 0.1, 0.3] meaning 60% this image is dog image, 10% is cat and 30% is bird. So, we need to caculate the loss (how far the prediction from the truth) and use it to adjust the network. 

The concept of cross-entropy helps us to acomplish this. Given the true distribution P (in our example, it can be [1,0,0] of dog class) and the estimated distribution Q (it is [0.6, 0.1, 0.3]), once cross-entropy H(P,Q) is calculated, we know how far it is from the theoricaly optimal one H(P,P). 
<p align="center">
<img src="/tex/0df95fcc730ff64df9bb063517904537.svg?invert_in_darkmode&sanitize=true" align=middle width=399.3958254pt height=49.3152198pt/>
</p>
