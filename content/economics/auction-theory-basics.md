---
title: Auction Theory Basics
description:
tags:
- economics
weight: 1
---

Auctions are allocation mechanisms[^munoz].

{{< info title="Notations">}}
Naively, an auction is observed to have several factors. To save keystrokes, we use a set of symbols to denote the variables:

1. the seller $\mathscr S$,
2. the bidders $\\{\mathscr B_i\\}$,
3. the object $\mathscr O$ to bid on,
4. the bidding prices $\\{b_i\\}$.

{{< /info >}}

In an auction, each bidder $\mathscr B_i$ decides on a valuation $v_i$ of the object $\mathscr O$ and bid with a bidding price $b_i$ based on the valuation.

The rules may be very different in different actions but they should have two components, how the object is allocated (**allocation rule**) and how the bidders are paying (**payment rule**). A simple yet interesting example of the payment rule is that of a Vickrey auction. Vickrey auction is a type of sealed-bid auction or blind auction, where the bidders have no information about the bidding price of other bidders. In a **Vickrey auction**, the winner pays the **second-highest price**[^Vickrey].

In general, we will observe that an auction has

1. the winner $\mathscr B_w$ who takes the object $\mathscr O$,
2. the losers $\mathscr B_l$,
3. the winner's payment $p_w$,
4. the losers' payment $p_l$.

In the above bullet points, 1 and 2 are determined by the allocation rules, while 3 and 4 are determined by the payment rules.

In auction theory, it is important to understand what the auction leads to, aka the equilibrium. To achieve this, we will come up with a formal representation of an auction in the following sections.



## Game, Mechanism, and Auction

The Bayesian game provides a good theoretical ground for auctions. A Bayesian game is defined by the setting and the mechanism. The setting is the stage and different mechanisms lead to different equilibria and properties.

{{< info title="Bayesian Game Setting">}}
A Bayesian game setting is defined by $(N, O, \Theta, p, u)$, where[^ShohamLeyton-Brown]

1. $N$ is a finite set of $n$ agents or players, e.g., bidders $\\{\mathscr B_i\\}$,
2. $O$ is a set of outcomes,
3. $\Theta$ is a set of possible types for each agent, e.g., a bidder can be type one who would squeeze in to get the deal, or type two who would avoid competitions,
4. $p$ is some prior probability (distribution) on types $\\{\theta_i\\}$, i.e., $p(\Theta)$, that is shared by all agents,
5. $u$ is a set of utility functions for all agents.

[^ShohamLeyton-Brown]: Y. Shoham and K. Leyton-Brown, “Multiagent Systems: Algorithmic, Game-Theoretic, and logical foundations”, 2008.

{{< /info >}}

{{< info title="Mechanism">}}

A mechanism is defined by $(A, M)$, where[^ShohamLeyton-Brown]

1. $A$ is a set of available actions for each agent, e.g., each bidder $\mathscr B_i$ has a set of available actions $a_i$,
2. $M$ is the map from actions to the distribution of outcomes.

With the mechanism defined, we will be able to design, implement, and measure the game.

[^ShohamLeyton-Brown]:  Y. Shoham and K. Leyton-Brown, “Multiagent Systems: Algorithmic, Game-Theoretic, and logical foundations”, 2008.

{{< /info >}}

The fact that auction is an allocation mechanism indicates that the outcome will be two parts, the **allocation** of the object $X$ and the **payment** $\mathbb{R}^n$ in an $n$ bidder auction. Comparing to the Bayesian game, we have the stage

1. $n$ bidders $\\{\mathscr B_i\\}$ as the agents,
2. the allocation $X$ together with the payment $\mathbb{R}^n$ are the outcomes,
3. the valuation structures are the types,
4. the probability distribution of the valuation structures is the common prior,
5. utility functions of the bidders as the utility functions.

We also have the mechanism

1. bidding at different prices as actions,
2. allocation rule (or choice rule) and payment rule map the actions to the allocation results $X$ and payment results $\mathbb{R}^n$, respectively.

{{< info title="Mechanism">}}

The way we split the mechanism map $M$ into $X$ and $\mathbb{R}^n$ makes it a quasilinear mechanism, which is defined by a triple $(A_i, \chi, \wp)$, where[^ShohamLeyton-Brown]

1. $A$ is a set of actions available to bidders $\\{B_i\\}$,
2. $\xi$ is the choice rule that maps actions to the distribution of allocations,
3. $\wp$ is the payment rule that maps actions to the payments.

[^ShohamLeyton-Brown]:  Y. Shoham and K. Leyton-Brown, “Multiagent Systems: Algorithmic, Game-Theoretic, and logical foundations”, 2008.

{{</info>}}


## Risk Attitude

Technically speaking, the valuation $v_i$ doesn't necessarily equate to the bidding price $b_i$ of bidder $\mathscr B_i$. The relation between valuation $v_i$ and bidding price $b_i$ is called the **bidding function**.

The payoff of $\mathscr B_i$ who bids with $b_i$ and valuation $v_i$ is $v_i - b_i$. The simplest definition of the utility function is

{{<math>}}
\begin{equation}
u_i = v_i - b_i.
\label{eqn-auction-utility-payoff}
\end{equation}
{{</math>}}

Notice that this utility function only depends on the choice of the bidder. Though useful, this definition doesn't reflect the personalities of the bidder. For the personalities, we introduce a new term related to the payment $p_i$, so that the utility becomes

{{<math>}}
\begin{equation}
u_i =  v_i - b_i - f_i,
\label{eqn-auction-utility-payoff-and-payment}
\end{equation}
{{</math>}}

where $f_i$ is a function of the payment. The risk attitude is best tested in a fair lottery where the expected payoff is the same as the investment. In such a fair lottery, the utility for \ref{eqn-auction-utility-payoff-and-payment} depends on the payment and the willingness to pay is different at different costs.

Risk neutral bidders are willing to participate at different costs based on payoff. Risk aversion bidders are less willing to participate at higher costs and risk seeking bidders are more willing to participate at higher costs[^ShohamLeyton-Brown].


## Types of Auctions

There exist many different types of auctions. Base on the allocation rules and payment rules, we may have first-price auction (FPA), second-price auction (SPA), English ascending-bid auction, Dutch descending-bid auction, etc[^Klemperer]. Shoham and Leyton-Brown have provided a list of canonical auctions in their book[^ShohamLeyton-Brown].

### First-price Auction

There are two key relations:

1. map from valuation $v_i$ to bid $b_i$, aka bidding function,
2. map from bidding $b_i$ to the probability of winning $P(\mathrm{win})$.

Given the probability of winning, valuation, and bid, one could usually calculate the expected utility $\bar U_i$ for risk neural bidders.

To measure the expected payoff of a bidding price $b_i$ for bidder $\mathscr B_i$, we introduce the expected utility, $\bar U_i$, e.g.,

\begin{equation}
\bar u_i = P(\mathrm{win}) (v_i - b_i) + P(\mathrm{lose}) 0 = P(\mathrm{win}) (v_i - b_i),
\end{equation}

where $P(\mathrm{win})$ is the probability of winning and $P(\mathrm{lose})$ is the probability of losing.





## References

[^munoz]: F. Muñoz-García, “An Introduction to Auction Theory for Undergraduate Students,” no. 509, pp. 1–19, 2012.
[^Vickrey]: W. Vickrey, “Counterspeculation, Auctions, and Competitive Sealed Tenders,” J. Finance, vol. 16, no. 1, p. 8, 1961.
[^Klemperer]: P. Klemperer, “Auction Theory: A Guide to the Literature.” .
[^ShohamLeyton-Brown]:  Y. Shoham and K. Leyton-Brown, “Multiagent Systems: Algorithmic, Game-Theoretic, and logical foundations”, 2008.