# Optimal Time of ET Sale in Secondary Market
We model the market of execution tickets (ETs) as that of auctions of block building right where the ticket holder endogeously time the sale initiation. The framework aims to explore a conjectured equivalence between ETs and the spot / just-in-time auctions as mediated by MEV-Boost. ET markets are defined before providing an auction model. For a revenue-, equivalently, MEV-maximizing, and risk neutral proposer, and the execution right matures in a finite period of time, if the proposer optimally sells the right closer to the expiry date, buyers of the ticket must exercise the prposing right immediately. The ET mechanism with deterministic maturity, therefore, becomes a spot auction that takes place at its maturity date. In other words, the ET holder exerts control over the exercise decision of the buyer, hence, the time of the spot auctions, which may spur censorship issues and centralize the ET supply. 

## ET Market
ET is a market that auctions off the right of proposing Consider the ET mechanism:

1. A protocol sells an exogenous supply of ETs to the group of validators. This first round of ET purchase directly from the protocol is the **_primary ET market_**. Each ET confers its holder the proposing right for some future block.

2. One ET is drawn for every block, where its holder wins the proposing right.

3. After the winner's proposal, its ticket is **burned** (permanently removed from the network), and simultaneously a new ET is **minted** (generated) to reiterate the primary market exchange.

A **_secondary ET market_** emerges exactly because of the **_forward nature_** of ETs. ETs may also come with a maturity, requiring that the proposing right be executed within a certain number of forthcoming blocks.

## The Model

We investigate the proposer's decision to sell the ET in the secondary market. Taking the primary ET market as exogenous, we model the secondary market as an auction of proposing rights, with the timing of the sale being endogenous. The model includes the following elements:

- **Risk-neutral, revenue/MEV-maximizing seller/ET holder** $\mathcal{S}$ with a discount rate $d \in (0,1)$.
- **Set of risk-neutral buyers** $i \in \mathcal{N} = \{1, \ldots, n\}$ with the same discount rate. Each buyer can exploit MEV (such as CEX-DEX arbitrage, atomic MEV) at a cost $\theta_i$, which is drawn i.i.d. from a distribution with support $[\underline{\theta}, \bar{\theta}]$.
- For simplicity, we assume no capital requirements for buyers to participate in the auction. To endogenize participation, we may introduce a capital cost $K \geq 0$ to explore the optimal timing of buyer participation.
- **Random variable** $\mathcal{R}$ represents the prize of execution layer rewards, which is the profit from winning the ET to exploit its issuance reward and MEV.
- Without loss of generality, consider an ET ticket of maturity $T \in \mathbb{N}$, with discrete time intervals.
