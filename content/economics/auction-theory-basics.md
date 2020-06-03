---
title: Auction Theory Basics
description:
tags:
- economics
weight: 1
---

Auctions is an allocation mechanism[^munoz].

{{< info title="What is an Auction">}}
An auction has four factors: the seller $\mathscr S$, the bidders $\\{\mathscr B_i\\}$, the object to be bidded on $\mathscr O$, and a set of rule $\\{\mathscr R_i\\}$ to determine the winner. Each bidder $\mathscr B_i$ decides on an valuation $v_i$ of the object $\mathscr O$.
{{< /info >}}

The rules may be very different but they should have two components, the allocation rule and the payment rule. A simple yet interesting example of the payment rule is that of the Vickrey auction. Vicker auction is a type of sealed bid auction or blind auction, where the bidders have no information about the bidding price of other bidders. In a **Vickrey auction**, the winner pays the **second highest price**[^Vickrey].

The outcome of the auction will be

0. the bidders offered bidding prices $\{b_i\}$,
1. the winner $\mathscr B_w$ who takes the object $\mathscr O$,
2. the winner's price $p_w$,
3. the losers $\mathscr B_l$,
4. the losers' price $p_l$.

In the following sections, we will come up with a formal representation of an auction.

## Expected Utility

The valuation $v_i$ doesn't necessariy equal to the bidding price $b_i$ of bidder $\mathscr B_i$. The relation between valuation $v_i$ and bidding price $b_i$ is called the **bidding function**.

To measure the payoff of a bidding price $b_i$ for bidder $\mathscr B_i$, we introduce the expected utility, $\bar U_i$, e.g.,

\begin{equation}
\bar u_i = P(\mathrm{win}) (v_i - b_i) + P(\mathrm{lose}) 0 = P(\mathrm{win}) (v_i - b_i),
\end{equation}

where $P(\mathrm{win})$ is the probability of winning and $P(\mathrm{lose})$ is the probability of losing.

## Game, Mechanism, and Auction

The Bayesian game provides a good theoretical ground for auctions. A Bayesian game is defined by the setting and the mechanism. The setting is the stage and different mechanisms lead to different equilibria and properties.

{{< info title="Bayesian Game Setting">}}
A Bayesian game setting is defined by $(N, O, \Theta, p, u)$, where[^ShohamLeyton-Brown]

1. $N$ is a finite set of $n$ agents or players, e.g., bidders $\\{\mathscr B_i\\}$,
2. $O$ is a set of outcomes,
3. $\Theta$ is a set of possibe types for each agent, e.g., a bidder can be type one who would squeeze in to get the deal, or type two who would avoid competitions,
4. $p$ is some prior probability (distribution) on types $\\{\theta_i\\}$, i.e., $p(\Theta)$, that is shared by all agents,
5. $u$ is a set of utility functions for all agents.

[^ShohamLeyton-Brown]: Y. Shoham and K. Leyton-Brown, “Multiagent systems: Algorithmic, Game-Theoretic, and logical foundations,” Multiagent Syst. Algorithmic, Game-Theoretic, Log. Found., vol. 9780521899, pp. 1–483, 2008.

{{< /info >}}

{{< info title="Mechanism">}}

A mechanism is defined by $(A, M)$, where[^ShohamLeyton-Brown]

1. $A$ is a set of available actions for each agent, e.g., each bidder $\mathscr B_i$ has a set of available actions $a_i$,
2. $M$ is the map from actions to the distribution of outcomes.

With the mechanism defined, we will be able to design, implement, and measure the game.

[^ShohamLeyton-Brown]: Y. Shoham and K. Leyton-Brown, “Multiagent systems: Algorithmic, Game-Theoretic, and logical foundations,” Multiagent Syst. Algorithmic, Game-Theoretic, Log. Found., vol. 9780521899, pp. 1–483, 2008.

{{< /info >}}

The fact that auction is an allocation mechanism indicates that the outcome will be two parts, the **allocation** of the object $X$ and the **payment** $\mathbb{R}^n$ in a $n$ bidder auction. Comparing to the Bayesian game, we have the stage

1. $n$ bidders $\\{\mathscr B_i\\}$ as the agents,
2. the allocation $X$ together with the payment $\mathbb{R}^n$ are the outcomes,
3. the valuation strutures are the types,
4. the probability distribution of the valuation structures is the common prior,
5. utility functions of the bidders as the utility function.

We also have the mechamism

1. bidding at different time and prices as actions,
2. allocation rule (or choice rule) and payment rule maps the actions to the allocation results $X$ and payment results $\mathbb{R}^n$.

{{< info title="Mechanism">}}

The way we split the mechamism map $M$ into $X$ and $\mathbb{R}^n$ makes it a quasilinear mechamism, which is defined by a triple $(A_i, \chi, \wp)$, where[^ShohamLeyton-Brown]

1. $A$ a set of actions available to bidders $\\{B_i\\}$,
2. $\xi$ is the choice rule that maps actions to distribution of allocations,
3. $\wp$ is the payment rule that maps actions to the payments.

[^ShohamLeyton-Brown]: Y. Shoham and K. Leyton-Brown, “Multiagent systems: Algorithmic, Game-Theoretic, and logical foundations,” Multiagent Syst. Algorithmic, Game-Theoretic, Log. Found., vol. 9780521899, pp. 1–483, 2008.

{{</info>}}


## Types of Auctions

There exists many different types of auctions. Base on the allocation rules and payment rules, we may have first-price auction (FPA), second-price auction (SPA), English ascending-bid auction, Dutch descending-bid auction, etc[^Klemperer]. Shoham and Leyton-Brown show a list of canonical auctions in their book[^ShohamLeyton-Brown].



### First-price Auction

There are three key relations:

1. map from valuation $v_i$ to bid $b_i$, aka bidding function,
2. map from bidding $b_i$ to probability of winning $P(\mathrm{win})$.

Given the probability of winning, valuation, and bid, one could usually calculate the expected utility $\bar U_i$.




## References

[^munoz]: F. Muñoz-García, “An Introduction to Auction Theory for Undergraduate Students,” no. 509, pp. 1–19, 2012.
[^Vickrey]: W. Vickrey, “Counterspeculation, Auctions, and Competitive Sealed Tenders,” J. Finance, vol. 16, no. 1, p. 8, 1961.
[^Klemperer]: P. Klemperer, “Auction Theory: A Guide to the Literature.” .
[^ShohamLeyton-Brown]: Y. Shoham and K. Leyton-Brown, “Multiagent systems: Algorithmic, Game-Theoretic, and logical foundations,” Multiagent Syst. Algorithmic, Game-Theoretic, Log. Found., vol. 9780521899, pp. 1–483, 2008.