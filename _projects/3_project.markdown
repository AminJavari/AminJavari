---
layout: page
title: Role-based Profiling
description: A role-based model to profile users in networks with multi-type of interactions. 
img: /assets/img/p3-1.png
importance: 3
---

In real-world networks, nodes might have more than one type of relationship. Signed networks are an important class of such networks consisting of two types of relations: positive and negative. In this project, we focus on signed networks as a representative example of network with multi-type connections. Recently, embedding signed networks (as a way to profile nodes/users) has attracted increasing attention. <br>

Most existing network embedding methods have been designed for networks with only a single edge type and where relations between two nodes implies closeness. Hence, they primarily try to encode an unsigned network in a way that neighboring nodes (nodes connected through paths) are closer in the embedding space. However, The underlying principles of signed networks can be quite different since a path between nodes does not necessarily indicate their closeness. Existing works capture the complex relationships by relying on social theories like balance theory. However, this approach has major drawbacks, including the incompleteness/inaccurateness of such theories. <br> 


We propose network transformation based embedding to address these shortcomings. The core idea is that rather than directly finding the similarities of two nodes from the complex paths connecting them, we can obtain their similarities through simple paths connecting their different roles. The idea can be employed for node embedding in networks with multi-type of connections. More specifically, to embed signed networks, we introduce a ROle based Signed network Embedding (ROSE) that bypasses the aforementioned challenges. The underlying idea is to transform the signed network into a bipartite network where each node takes both user and item roles for which they are the giver and receiver of signed links, respectively. Therefore, each node of a signed network can be modeled by a set of roles, denoted as role-nodes, where the relations between role-nodes can be fully captured using unsigned links. Then, ultimately this transformed network can utilize the state of the art unsigned embedding technique. The following figure is a toy example of the transformation process. <br>

<div class="text-center">

    <div class="col-sm mt-3 mt-md-1">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/p3-2.png' | relative_url }}" alt="" style="width: 400px" title="Toy example 1"/>
    </div>
</div>
<div class="caption">
      Transformation of a signed network with two nodes to an unsigned bipartite network of role-nodes.
</div>


Since each role-node captures a certain aspect of an original node, the embedding vector of a target node can be derived by aggregating the embeddings of the corresponding role-node. In sum, a network transformation based embedding model can be described in three main steps: 1) Network transformation. 2) Embedding the transformed network. 3) Embedding the original network by aggregating the embeddings of the transformed network. Our experiments show the novel proposed technique substantially outperforms existing models. 


<div class="text-center">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/p3-3.pdf' | relative_url }}" alt="" style="width: 500px" title="Toy example 1"/>
    </div>
</div>
<div class="caption">
     Transformation of the input signed network to the embeddings of the corresponding role-nodes.
</div>






