---
layout: page
title: Hashtag Recom
description: An efficient hashtag recommendation model based on graph data. 
img: /assets/img/p2-1.png
importance: 1
---

Personalized hashtag recommendation for users could substantially promote user engagement in microblogging websites; users can discover microblogs aligned with their interests. However, user profiling on microblogging websites is challenging because most users tend not to generate content. Our core idea is to build a graph-based profile of users and incorporate it into hashtag recommendation. Indeed, user's followee/follower links implicitly indicate their interests. Considering that microblogging networks are scale-free networks, to maintain the efficiency and effectiveness of the model, rather than analyzing the entire network, we model users based on their links towards hub nodes. In fact, it can be said that hub-nodes on microblogging websites represent user's interests. The following figure illustrates the intuition behind the informativeness of hub nodes in determining what hashtags a user might be interested in. It depicts the distributions of the links that two sets of users have towards a small set of hub nodes in the US politics in which followers of a republican leader are more likely to use hashtag \#MAGA while the followers of a democrat leader tend to use hashtag \#VoteDem. <br>

<div class="text-center">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/p2-2.pdf' | relative_url }}" alt="" style="width: 500px" title="Toy example 1"/>
    </div>
</div>

<div class="caption">
     The percentage of links toward 10 representative nodes in the US politics for two groups: users who tweeted hashtag \#VoteDem and users who tweeted \#MAGA.
</div>



Based on this insight, our key idea is that in a microblogging website, the embeddings of nodes can be derived by aggregating the embeddings of the hub nodes they are connected to. That is, rather than finding the embeddings of entire nodes in the network, we can obtain the embeddings of hub nodes and build a function to transitively embed other nodes. We use this general idea as the basis of our hashtag recommendation model, i.e.,  we pick a set of hub users denoted as representative nodes and project those nodes and hashtags into a shared latent space. The following figure illustrates this idea. To predict the relevance of a give user to a given hashtag, a projection of the user is built by aggregating the embeddings of her hub neighbors guided by an attention model and then compared with the hashtag. Classically, attention models can be trained in an end to end manner. However, due to the high complexity of our problem, we propose a novel weak supervision model for the attention component, which significantly improves the effectiveness of the model. We performed extensive experiments on two datasets collected from Twitter and Weibo, and the results confirm that our method substantially outperforms the baselines.

 <br>

<div class="text-center">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/p2-3.pdf' | relative_url }}" alt="" style="width: 500px" title="Toy example 1"/>
    </div>
</div>

<div class="caption">
     A toy example representing the hashtags and representative nodes related to politics and soccer in a shared latent space
</div>







