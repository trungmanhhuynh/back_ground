"Entropy" term is invented by Claude Shannon, who is the father of information theory.
Shannon defined the **entropy as the smallest possible average size of lossless encoding of the messages sent from the source to the destination.**

For example, the entropy answers the question if one sends 4 types of messages (fine, cloudy, rainy, snow), how many minimum bits each message should be encoded?. So, if 4 messages were sent with the same probability 25% assuming each time we send one message, thus we need to use 2 bits to encode each message. However, it is not a real case. The probability of sending a message could be different; for instance, messages of "fine" could be 50% meaning that it will be sent every 2 messages, or "cloudy" could be 25% meaning it is sent every 4 messages. Thus, for "fine" we should use less bit while "cloudy" should be encoded with more bits. In overall, Shannon said that the number of minimum bits used to encode each message is <img src="https://latex.codecogs.com/svg.latex?\fn_cm&space;log_2(N)" title="log_2(N)" /> , where N is the number of message types.


It easy to understand that this formula is correct in the scenario that the probabilities of all message types
are equal (let's say 12.5% for 8 message types). We need to use 3 bits to encode each message. However, it is interesting that this formula is also correct for the different probability message types. For example, if the probability "fine" is 50% then it should be encoded with log(2) = 1 bit; "cloudy" is 25%, thus it should be encoded with log(4) = 2 bits, and so on.

We also know that:
log(N) = -log(1/N) = -log(p(x)), where p(x) = 1/N. This is very interesting because, given the probability of each message type, we are able to calculate the minimum bits required to encode it. yay!



<img src="/tex/d62fbe219457fce60682a162b4ecbab4.svg?invert_in_darkmode&sanitize=true" align=middle width=124.40236709999998pt height=24.65753399999998pt/> 
***
I learned a lot from these great articles
1. [Demystifying Entropy](https://towardsdatascience.com/demystifying-entropy-f2c3221e2550) by Naoki Shibuya 


