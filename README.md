# Graph-Neural-Networks-As-Transformers

Ever since transformers were introduced by Vaswani et. al. in 2017, we also see their applications in fields like Computer Vision (Vision Transformers) and now in Geometric Deep Learning. However, there are so many ideas and variants of using transformers in graphs that the concepts could be a little overwhelming. In this repo, I will try my best to briefly explain the main concepts of the major variants of Graph Transformers

But firstly, why even use transformers in graphs? Well, the answer to this question lies in the fundamental concept of transformers : The Attention Mechanism. Just as the attention mechanism helps the model to capture the most relevant words in a sentence, it could also be used to identify certain nodes in the graph which are more important than others. As an example, lets say we try to use graphs to predict social relations in twitter. If we consider an influencer like Elon Musk, he would have more connections compared to most individuals and thus would become an important node to make accurate predictions. (quite a vague example but I hope you get the point)

