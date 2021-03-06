# Entropy is a beatiful formula 

"Entropy" term is invented by Claude Shannon, who is the father of information theory.
Shannon defined the **entropy as the smallest possible average size of lossless encoding of the messages sent from the source to the destination.**

For example, the entropy answers the question if one sends 4 types of messages (fine, cloudy, rainy, snow), how many minimum bits each message should be encoded?. So, if 4 messages were sent with the same probability 25% assuming each time we send one message, thus we need to use 2 bits to encode each message. However, it is not a real case. The probability of sending a message could be different; for instance, messages of "fine" could be 50% meaning that it will be sent every 2 messages, or "cloudy" could be 25% meaning it is sent every 4 messages. Thus, for "fine" we should use less bit while "cloudy" should be encoded with more bits. In overall, Shannon said that the number of minimum bits used to encode each message is $log_2(N)$ , where N is the number of message types.


It easy to understand that this formula is correct in the scenario that the probabilities of all message types
are equal (let's say 12.5% for 8 message types). We need to use 3 bits to encode each message. However, it is interesting that this formula is also correct for the different probability message types. For example, if the probability "fine" is 50% then it should be encoded with $log(2) = 1$ bit; "cloudy" is 25%, thus it should be encoded with $log_2(4) = 2$ bits, and so on.

We also know that:
$log_2(N) = -log_2(1/N) = -log_2(p(x))$, where $p(x) = 1/N$. This is very interesting because, given the probability of each message type, we are able to calculate the minimum bits required to encode it. yay!

The  minimum bits to encode all messages is thus:
<p align="center"> $Entropy =  - \sum_{i=1}p(x)log_2p(x) $ -- a well-known formula </p>

**Entropy is thus related to the following terms:**

**uncertainty/disorder/unpredicability/surprise/amount of information**: when entropy is high (the averaged number of bits used to encode are high), we have more messages with low probabilities. Thus, when a message is received, we dont expect that this is the same message we received as the previous one. We says it is high uncertainty or disorder or upredicability. So, high entropy ~ high uncertainly. When the same low probability message is received, it is a surprise. Also, high entropy indicates a high amount of information (a high number of encoding bits) or the information in each message is less predicatable and more specific/values.


***
I learned a lot from these great articles
1. [Demystifying Entropy](https://towardsdatascience.com/demystifying-entropy-f2c3221e2550) by Naoki Shibuya 


