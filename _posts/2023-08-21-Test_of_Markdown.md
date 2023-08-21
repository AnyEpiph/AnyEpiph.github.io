---
layout: post
title: "测试页面"
date:   2023-08-20
tags: [test]
comments: false
author: AnyEpiph
---

作为一个程序员怎么能没有自己的个人博客呢，这里详细记录和分享我的博客搭建经验，让你轻轻松松拥有自己的博客网站。傻瓜式一站式教你用 github pages 来搭建博客，详细记录全过程，保证你能学会。

如果你是非程序员或者不关系技术细节，只需花 3 分钟阅读前面 5 个章节内容，就能轻松拥有自己的博客。

<!-- more -->

# Reviewers’ opinion

Last Update: 2023/03/03

## Summary：

- **General Review**
    - **Highlights should be improved**
        - Passenger loss due to long waiting time is common. (Reviewer #2)
        - Highlights about *developing a robust method based on RO*, and *conducting sensitivity analysis on parameters* is lack of innovation. (Reviewer #2)
        - Highlights should be improved. (Reviewer #3)
- **Abstract**
    - **Give more information**
        - Model and control methods should be mentioned more specifically in abstract. (Reviewer #3)
- **Introduction**
    - **Show motivation**
        - Why choose robust optimization methods rather than other methods? (Reviewer #3)
- **Model Description**
    - **Model Assumptions**
        - Assumptions are too strong, may lead to some mistake. (Reviewer #2)
        - Assumptions of Formula (1) is related to doors, mention “one door assumption” will be better. (Reviewer #1)
    - **Derivations**
        - Provide more details for the derivation of Formula (7). (Reviewer #1)
        - Explain how to calculate the passenger loss rate at the i-th station in Formula (9).  (Reviewer #1)
        - The decision variables is not clear. At-station and Inter-station control are not clearly formulate in the objective function (Formula (11)-(13)). (Reviewer #1)
    - **Other**
        - Lack of descriptions about how inter-station control is implemented. (Reviewer #2)
        - Explain the meaning of “non-negative adjustments”. (Reviewer #1)
        - Show the motivation of Figure 1, what does it want to show?  (Reviewer #3)
        - Will the solutions of the RO method be too conservation or not solvable?  (Reviewer #2)
- **Methods & Algorithms**
    - **Methods**
        - Elaborate more about how the solution algorithm works, includes how to implement, the running time and the environment.  (Reviewer #1&2)
        - Compare the proposed method with common rule-based bus control methods to illustrate its effect. (Reviewer #2)
    - **Algorithms**
        - What's the motivation of the algorithms? The introduction and description seem to be lacking. (Reviewer #2)
        - Please analyze the property of the solution obtained from the proposed algorithm. (Reviewer #2)
    - **Simulations**
        - Emphasize more on the stability as it is the topic of your paper. (Reviewer #1)
        - Show the motivation of the simulation scenarios. Does the parameter setting in the case come from practical operations? (Reviewer #2&3)
        - Why not consider a real-world scenario? (Reviewer #1&2)
        - Elaborate the colors' meaning in Figure 3.  (Reviewer #1)
        - More comparisons with the state-of-the-art are needed. (Reviewer #3)
        - Are the current computational results instructive for practical bus operations? (Reviewer #2)

## Raw Review

**Reviewer #1**

Accounting for Passenger Loss in Bus Bunching Reduction: A Robust Optimization Approach

The paper addresses the bus bunching simulation and optimization problem by considering passenger loss due to long waiting time. A robust optimization model is developed considering the uncertainties in bus running times and passenger boarding times. Simulation experiments are conducted to show the benefits of considering passenger loss in bus bunching optimization. The paper is interesting and extends the previous studies on bus bunching modelling and simulation. Below are some comments for further revisions.

1, It is not clear what the decision variables are in the formulated models (13) and (14). It is also not clear what kinds of at-station and inter-station control strategies are considered in the studies, and how these control strategies are formulated in the optimization model.

2, For Eq. (1), it is related to the number of doors of the transit vehicles. Thus, I think you may add an assumption about it.

3, Please provide more details on the derivation of Eq. (7). What does the integral part mean and how to get the final result?

4, Please elaborate more on how to calculate the passenger loss rate at the i-th station.

5, Please elaborate more on the implementation of the solution algorithm; that is, how it is implemented and how long it takes to solve the model.

6, Except for numerical simulations, it will be better to provide a real-life case study to show the benefits.

7, The language should be further edited and polished. Currently, there are several errors that reduced the clarity and readability of the paper.

8, Since you mentioned that your model can improve the stability of a bus system. So, please elaborate more on how the model can improve the stability.

9, What do negative and non-negative adjustments mean?

10, In Figures 3-4, you should clarify the meaning of the color lines.

**Reviewer #2**

This paper describes a bus control model considering passenger loss during waiting, and designs a control method based on robust optimization. Numerical experiments are implemented to test the effectiveness and robustness of the control method. 

For the current version of the manuscript, I have great concerns about the innovation of this paper, and I question how realistic the proposed approach will be in practice.

The authors claim to provide three main contributions: considering the effect of passenger loss, developing a robust method based on RO, and conducting sensitivity analysis on parameters. Unfortunately, I fail to agree with the authors that these contributions are particularly relevant. Considering passenger loss due to too long waiting times is common in optimization issues of many transport systems. Robust optimization and sensitivity analysis for bus control problems are certainly not novelties, which were already described in extensive literature. The following are other major comments.

1. In section 2, many idealized assumptions (both explicitly and implicitly) are adopted in this paper, the rationality analysis and application scenarios of which are not mentioned. I question how realistic this control method will be in practice. For instance, bus overtaking is very common in practice, unlimited capacity makes the model unsuitable for rush hours, and ignoring passengers' deboarding time is unreasonable for stops with high alighting demands.

2. Inter-station control is considered in this paper, but it is not mentioned how it is implemented and what technologies are required. It is recognized that bus operations are highly uncertain. Under the influence of traffic lights, jams, accidents, etc., how to ensure the effectiveness of inter-station control? How realistic is that?

3. For the robust optimization method adopted in this study, the optimization is based on the worst case to make the solution robust enough to any situation. In this case, the solution will become more conservative, which may lead to the solution be infeasible.

4. In Section 3, what motivates the algorithm? The introduction and description of Algorithm 2 seem to be lacking. Besides, please analyze the property of the solution obtained from the proposed algorithm.

5. In Section 4, why not consider a real-world scenario? Are the current computational results instructive for practical bus operations? Does the parameter setting in the case come from practical operations? Please motivate the chosen parameters.

6. In Section 4, the computation time is not mentioned while it is essential for bus operational problems. Besides, it is not mentioned the software and language used to implement the algorithm. It is suggested to compare the proposed method with common rule-based bus control methods to illustrate its effect.

**Reviewer #3**

1. Highlights should be improved.

2. The proposed model and control method should be informative in the abstract.

3. The contributions of this manuscript are questionable:

1) Regarding the literature, it is not convincing that the existing literature ignores passenger loss, and the author should explain why this research gap exists. What are the challenges (difficulties) when considering the passenger loss for the bus bunching problem?

2) The author should better motivate the choice of robust optimization, why not another method?

4. The authors should better motivate the model presented in Figure1. It is kind of surprising there is no support reference when introducing the model in Figure 1.

5. The simulation results are also unconvincing.

1) Without any motivation, simulation scenarios are simply defined.

2) More comparisons with the state-of-the-art are needed.

To sum up, this paper needs a significant improvement and this manuscript's quality is far below TRB's expectations.
