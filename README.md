# Graph-Neural-Networks-As-Transformers

Ever since transformers were introduced by Vaswani et. al. in 2017, we also see their applications in fields like Computer Vision (Vision Transformers) and now in Geometric Deep Learning. However, there are so many ideas and variants of using transformers in graphs that the concepts could be a little overwhelming. In this repo, I will try my best to briefly explain the main concepts of the major variants of Graph Transformers

But firstly, why even use transformers in graphs? Well, the answer to this question lies in the fundamental concept of transformers : The Attention Mechanism. Just as the attention mechanism helps the model to capture the most relevant words in a sentence, it could also be used to identify certain nodes in the graph which are more important than others. As an example, lets say we try to use graphs to predict social relations in twitter. If we consider an influencer like Elon Musk, he would have more connections compared to most individuals and thus would become an important node to make accurate predictions. (quite a vague example but I hope you get the point)

Graphormers (Ying, 2021)

In the graphormer paper, the authors looked at three main ideas:-

1) Centraility Encoding : This is basically the Elon Musk example I have mentioned. The importance of a node in a graph is captured by calculating the number of in and out degrees of a node (i.e, the number of connections entering and leaving a node respectively).

2) Spatial Encoding : The attention weights in a graphormer is very similiar to the classical formula introduced in the original paper. The main differences being the introduction of learnable weight matrices multiplied to the q,k,v pairs followed by a leanable bias vector b added to the attention weights. This bias is a function of the spatial relationship between two nodes (i,j). This function could be several things. In the paper, they considered the shortest distance between i and j if te nodes are connected and -1 if they are not connected. If b is learnt as a decreasing function, the model would pay more attention to nearby nodes.

3) Edge encoding : In a typical GNN, what most architectures do is just concatenate the edge features with the associated node features (i,e to whichever nodes these edges connect). However, in a single message passing layer, by doing so, we would not use this information on the whole graph (if we wanted to make graph-level predictions). We could possibly do this using multiple message passing layers, but for a graph with very large number of nodes, we would end up with the problem of oversmoothing if we try to use too many message passing layers. In edge encoding, the edge information is ingrained along the shortest path between the nodes i,j.

Interestingly, the authors also observed no oversmoothing in Graphormers.

