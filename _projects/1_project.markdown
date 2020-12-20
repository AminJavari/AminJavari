---
layout: page
title: User Discovery
description: A graph-based user retrieval system on Twitter to discover users with certain interests. 
img: /assets/img/p1-1.png
importance: 2
---

We introduce a novel interest-based discovery system on Twitter to discover and search for users with certain interest patterns. Although, a user discovery system is beneficial in various applications like viral marketing and online advertising, to the best of our knowledge, this is first attempt to design such a system. Towards building the system, we encounter two key design questions. How can an interest-based query be defined? What data source can be leveraged to build the system? We suggest to define input queries based on the notion of query by example as it is a powerful methodology in capturing complex queries. Also, we propose to use follower connections between users to construct the system as it implicitly exhibits users’ interest and it is more abundant than other data sources. Based on these answers, we formulate the task of building the discovery system as solving a novel problem denoted as interest aware seed expansion, i.e., given a seed set of users representing a certain interest pattern, we aim to identify other users sharing the same interest patterns by analyzing their connections. The key idea behind the model involves extracting the linkage patterns that reflect the shared interest pattern of seed users and discovering other users with the similar linkage patterns. <br>

However, since analyzing the entire network does not comply with the requirements of the problem in terms of efficiency, we aim to solve the problem by introducing the notion of representative nodes. As most links on Twitter represent users interests, we recognize popular nodes in the network as precious elements to effectively and efficiently address the problem. In fact, for each topic of interest there exist a set of representative nodes (hub nodes) on Twitter, and they receive a large proportion of the links representing the topic. As such, give a seed set of users, by analyzing their immediate neighbors, we can identify hub-nodes associated with target interest topics which allows us to identify the structure of the input query. Eventually, we can discover other users on the network with similar linkage patterns towards the identified representative nodes. To this end, we introduce a link generative process for seed users outgoing connections denoted as query-driven topic modeling. We carried out comprehensive experiments to evaluate different aspects of the model. The results verify the effectiveness of the proposed system. 

<div class="text-center">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/p1-2.png' | relative_url }}" alt="" style="width: 500px" title="Toy example 1"/>
    </div>
</div>
<div class="caption">
    A toy example demonstrating the links of a seed set of users and candidate users towards a selected set of representative. The seed set represents an interest pattern with two disjunctive interest combinations: a) users interested in Democrats, b) users interested in Republicans and Pop music. The model identifies the groups of representative nodes associated with each of the interest topics involved in the query. Consequently we can discover the structure of the query. Finally, we can decide if a certain candidate user should be retrieved as a related user to the given query. 
</div>





