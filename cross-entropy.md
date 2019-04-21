
# Cross-entropy: an exiting concept and its application in reducing loss. 

In image classifications, what we want is for the network model to predict correct images of dogs, cats, etc...

Let's say we a set of images in 3 classes of animals: dogs, cats, birds. In form of hot-encoding vectors and for the ease 
of training a network, dog class can be represented as a vector of [1,0,0]; cat is [0,1,0]; bird is [0,0,1]. The ideal model
will predict a test images belong to one of these classes. However, the reality is not. For a given test image, a model 
can predict it as [0.6, 0.1, 0.3] meaning 60% this image is dog image, 10% is cat and 30% is bird. So, we need to caculate the loss (how far the prediction from the truth) and use it to adjust the network. 

The concept of cross-entropy helps us to acomplish this. Given the true distribution P (in our example, it can be [1,0,0] of dog class) and the estimated distribution Q (it is [0.6, 0.1, 0.3]), once cross-entropy H(P,Q) is calculated, we know how far it is from the theoricaly optimal one H(P,P). 
<p align="center"> <img src="/tex/aa7e20514855d6bf3fb21d2e2de6ce3a.svg?invert_in_darkmode&sanitize=true" align=middle width=366.51908204999995pt height=24.657735299999988pt/> </p>

<p align="center"> <img src="/tex/4bdc5dd35f72d9085a529bc76f6a7f09.svg?invert_in_darkmode&sanitize=true" align=middle width=366.9950394pt height=24.657735299999988pt/> </p>

In information theory, <img src="/tex/67f4339f01ef1283c1af5592fadcc0b6.svg?invert_in_darkmode&sanitize=true" align=middle width=138.1264731pt height=24.65753399999998pt/> is how many redundant bits to encode messages from the theorically minimum ones.
In image classification, because we use one-hot encoding mechanism and <img src="/tex/0ae047b1e4a6d17d5b5329e7cacf1b52.svg?invert_in_darkmode&sanitize=true" align=middle width=42.63139649999999pt height=24.65753399999998pt/> is 0, the <img src="/tex/ba9cea0aa0038424952f45c90de9c5d3.svg?invert_in_darkmode&sanitize=true" align=middle width=59.096967599999985pt height=24.65753399999998pt/> is itself the distance (loss) from the truth distribution. Using example above, the loss of predicting that image is (given we've already know it is dog image) is: 
<p align="center"> <img src="/tex/e848f03c7d7cc38a9192604a1e4c5731.svg?invert_in_darkmode&sanitize=true" align=middle width=646.5493947pt height=24.657735299999988pt/>  </p>

Thus, we can see if the model predict the dog image correctly ([1,0,0]), the loss H(P,Q) is 0, while if it predict incorrectly [0.01, 0.99, 0], H(P,Q) is 4.6.  The negative log curve (loss) should be like this: 
![alt text](http://www.sosmath.com/algebra/logs/log4/log42/log422/gl30.gif)

 - In image classificaion, since the prediction probability is always from 0-1, thus the average loss if calculated correctly is only range from ~4 and gradually reducing to 0. In other applications, if the probability is not scaled well, the loss could be negative. 
 - In machine learnimg, natural log (log base e) is commonly used instead of log base 2. This is becaseu natural log is compatible with the derivative when calculting gradients, while log base 2 is not. Note that log base 2 is conventional and it is intuitive in information because it respresents the number of bits encoded (log(0.5) is 2 bits). Log base e does not represent any metrics; however, it is well-suited for the purpose of minimizing loss.
 
 Articles: 
 - [Demystifying Cross-Entropy](https://towardsdatascience.com/demystifying-cross-entropy-e80e3ad54a8) by  Naoki Shibuya
 
