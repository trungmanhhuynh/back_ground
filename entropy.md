# Entropy is a beatiful formula 

"Entropy" term is invented by Claude Shannon, who is the father of information theory.
Shannon defined the **entropy as the smallest possible average size of lossless encoding of the messages sent from the source to the destination.**

For example, the entropy answers the question if one sends 4 types of messages (fine, cloudy, rainy, snow), how many minimum bits each message should be encoded?. So, if 4 messages were sent with the same probability 25% assuming each time we send one message, thus we need to use 2 bits to encode each message. However, it is not a real case. The probability of sending a message could be different; for instance, messages of "fine" could be 50% meaning that it will be sent every 2 messages, or "cloudy" could be 25% meaning it is sent every 4 messages. Thus, for "fine" we should use less bit while "cloudy" should be encoded with more bits. In overall, Shannon said that the number of minimum bits used to encode each message is <img src="/tex/35ed3ca340b40e6a05e9546dd69757da.svg?invert_in_darkmode&sanitize=true" align=middle width=56.19684014999999pt height=24.65753399999998pt/> , where N is the number of message types.


It easy to understand that this formula is correct in the scenario that the probabilities of all message types
are equal (let's say 12.5% for 8 message types). We need to use 3 bits to encode each message. However, it is interesting that this formula is also correct for the different probability message types. For example, if the probability "fine" is 50% then it should be encoded with <img src="/tex/29fe1194e11dbaab86181bd3455d9585.svg?invert_in_darkmode&sanitize=true" align=middle width=72.76823565pt height=24.65753399999998pt/> bit; "cloudy" is 25%, thus it should be encoded with <img src="/tex/4452195ef62e364d9ce375405e28c596.svg?invert_in_darkmode&sanitize=true" align=middle width=79.55292014999999pt height=24.65753399999998pt/> bits, and so on.

We also know that:
<img src="/tex/8edf3f2443f66ed8dba77faa12426f10.svg?invert_in_darkmode&sanitize=true" align=middle width=268.97284095pt height=24.65753399999998pt/>, where <img src="/tex/a96ba097f291304219ff756b90ea1b0f.svg?invert_in_darkmode&sanitize=true" align=middle width=82.89378405pt height=24.65753399999998pt/>. This is very interesting because, given the probability of each message type, we are able to calculate the minimum bits required to encode it. yay!

The  minimum bits to encode all messages is thus: \
<p align="center">
  Entropy =  - \sum_{i=1}p(x)log_2p(x) $ -- a well-known formula
</p>


***
I learned a lot from these great articles
1. [Demystifying Entropy](https://towardsdatascience.com/demystifying-entropy-f2c3221e2550) by Naoki Shibuya 


