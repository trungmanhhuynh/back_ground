
# Cross-entropy: an exiting concept and its application in reducing loss. 

In image classifications, what we want is for the network model to predict correct images of dogs, cats, etc...

Let's say we a set of images in 3 classes of animals: dogs, cats, birds. In form of hot-encoding vectors and for the ease 
of training a network, dog class can be represented as a vector of [1,0,0]; cat is [0,1,0]; bird is [0,0,1]. The ideal model
will predict a test images belong to one of these classes. However, the reality is not. For a given test image, a model 
can predict it as [0.6, 0.1, 0.3] meaning 60% this image is dog image, 10% is cat and 30% is bird. So, we need to caculate the loss (how far the prediction from the truth) and use it to adjust the network. 

The concept of cross-entropy helps us to acomplish this. Given the true distribution P (in our example, it can be [1,0,0] of dog class) and the estimated distribution Q (it is [0.6, 0.1, 0.3]), once cross-entropy H(P,Q) is calculated, we know how far it is from the theoricaly optimal one H(P,P). 
<p align="center"> $H(P,P) = - \sum_iP(x)log(P(x)) = \mathbb{E}_{x \sim P }[-logP(x)] $ </p>

<p align="center"> $H(P,Q) = - \sum_iP(x)log(Q(x)) = \mathbb{E}_{x \sim P }[-logQ(x)]$ </p>

In information theory, $H(P,Q) - H(P,P)$ is how many redundant bits to encode messages from the theorically minimum ones.
In image classification, because we use one-hot encoding mechanism and $log(1)$ is 0, the $H(P,Q)$ is itself the distance (loss) from the truth distribution. Using example above, the loss of predicting that image is (given we've already know it is dog image) is: 
<p align="center"> $H(P,Q) = - \sum_iP(x)log(Q(x)) = - (1log(0.6) + 0log(0.1) +0log(0.3)) = -log(0.6) = 0.51 $  </p>

Thus, we can see if the model predict the dog image correctly ([1,0,0]), the loss H(P,Q) is 0, while if it predict incorrectly [0.01, 0.99, 0], H(P,Q) is 4.6.  The negative log curve (loss) should be like this: 
![alt text](https://www.google.com/search?q=negative+natural+log+curve&source=lnms&tbm=isch&sa=X&ved=0ahUKEwiPuPbTpuLhAhWOtp4KHS1WC5gQ_AUIDigB&biw=1344&bih=726#imgrc=6SrdjyDzgHuVLM:)
