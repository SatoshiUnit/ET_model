# Optimal Time of ET Sale in Secondary Market
We model the market of execution tickets (ETs) as that of auctions of block building right where the ticket holder endogeously time the sale initiation. The framework aims to explore a conjectured equivalence between ETs and the spot / just-in-time auctions as mediated by MEV-Boost. ET markets are defined before providing an auction model. For a revenue-, equivalently, MEV-maximizing, and risk neutral proposer, and the execution right matures in a finite period of time, if the proposer optimally sells the right closer to the expiry date, buyers of the ticket must exercise the prposing right immediately. The ET mechanism with deterministic maturity, therefore, becomes a spot auction that takes place at its maturity date. In other words, the ET holder exerts control over the exercise decision of the buyer, hence, the time of the spot auctions, which may spur censorship issues and centralize the ET supply. 

## ET Market
ET is a market that auctions off the right of proposing Consider the ET mechanism:

1. A protocol sells an exogenous supply of ETs to the group of validators. This first round of ET purchase directly from the protocol is the **_primary ET market_**. Each ET confers its holder the proposing right for some future block.

2. One ET is drawn for every block, where its holder wins the proposing right.

3. After the winner's proposal, its ticket is **burned** (permanently removed from the network), and simultaneously a new ET is **minted** (generated) to reiterate the primary market exchange.

A **_secondary ET market_** emerges exactly because of the **_forward nature_** of ETs. ETs may also come with a maturity, requiring that the proposing right be executed within a certain number of forthcoming blocks.
