# mev-bibliography

## other aggregations 
1. Domothy's pbs links: https://notes.ethereum.org/@domothy/pbs_links. 

## big picture
1. Neutralizing the Dark Forest
   - https://pseudotheos.mirror.xyz/i7sv9SFb1e64W2ax_kYwp68O0M2NdACtOu9Hj12SPP8
   - Pseudo and Domothy - Oct 12, 2022 
2. Notes on PBS
   - https://barnabe.substack.com/p/pbs
   - Barnabé - Nov 8, 2022
3. Updates on PBS (devcon 2022)
   - https://www.youtube.com/watch?v=sQQ2UYB3qOI
   - Barnabé - Oct 12, 2022
4. A study of the transaction supply chain from CryptoKitties to MEV-Boost to PBS (devconnect 2022) 
   - https://www.youtube.com/watch?v=jQjBNbEv9Mg
   - Barnabé - May 22, 2022
5. Block building after the Merge (decvon 2022)
   - https://www.youtube.com/watch?v=KP5ppCRH0iM
   - Alex - Oct 13, 2022
6. MEV-Boost, How Does it Work & What’s Missing? (sbc 2022)
   - https://www.youtube.com/watch?v=PS9SlHGJlrU
   - Alex - Sep 7, 2022
7. MEV-boost: Merge ready Flashbots Architecture
   - https://ethresear.ch/t/mev-boost-merge-ready-flashbots-architecture/11177
   - Stephane - Nov 4, 2021
8. MEV on ETH2: MEV-boost, PBS, Danksharding... How do the pieces fit together? (devconnect 2022)
   - https://www.youtube.com/watch?v=OD54WfVuDWw
   - Vitalik - May 22, 2022
9. Proposer/block builder separation-friendly fee market designs
   - https://ethresear.ch/t/proposer-block-builder-separation-friendly-fee-market-designs/9725
   - Vitalik - June 4, 2021
10. How much can we constrain builders without bringing back heavy burdens to proposers?
    - https://ethresear.ch/t/how-much-can-we-constrain-builders-without-bringing-back-heavy-burdens-to-proposers/13808
    - Vitalik - October 1, 2022
11. Annotated Ethereum Roadmap
    - https://notes.ethereum.org/@domothy/roadmap
    - Domothy - Dec 28, 2022
12. MEV on ETH2: MEV-boost, PBS, Danksharding... How do the pieces fit together? (devconnect 2022)
    - https://www.youtube.com/watch?v=OD54WfVuDWw
    - Vitalik - May 22, 2022

## relevant codebases & infrastructure links
1. flashbots/mev-boost-relay
   - https://github.com/flashbots/mev-boost-relay
   - The canonical relay codebase. This is what we are building the [optimistic relay](https://github.com/flashbots/mev-boost-relay/pull/285) on top of.
2. flashbots/mev-boost
   - https://github.com/flashbots/mev-boost
   - The validator EL (geth-fork) for interacting with the external builder network.
3. flashbots/prysm
   - https://github.com/flashbots/prysm
   - The prysm fork used as the CL for the validation nodes of the relay and as the CL of the builder.
4. flashbots/builder
   - https://github.com/flashbots/builder
   - The geth fork used as the EL of the builder.
5. flashbots/block-validation-geth
   - https://github.com/flashbots/block-validation-geth
   - The geth fork used as the EL of the validation nodes in the relay.
6. relayooor/geth
   - https://github.com/relayooor/go-ethereum
   - The geth fork used for the validation nodes of relay. Removes a few constraints from flashbots/block-validation-geth.
7. flashbots/prio-load-balancer
   - https://github.com/flashbots/prio-load-balancer
   - The router that sits between the relay and the validation nodes and queues blocks.
8. flashbots/relays-specs
   - https://github.com/flashbots/relay-specs
   - Defines the API for the relay data API and block submission.
9. ethereum/builder-specs
   - https://github.com/ethereum/builder-specs
   - Defines the API for validators to outsource block building (naming is a bit confusing here, this is the API the proposer uses to talk to the relay, not the block builder).
10. ralexstokes/mev-rs
    - https://github.com/ralexstokes/mev-rs
    - Rust toolkit for builders & builder network.
11. ralexstokes/relay-monitor
    - https://github.com/ralexstokes/relay-monitor
    - A service to monitor the behavior of relays.

## mev-boost (the software) r & d
1. Running mev-boost at scale
   - https://flashbots.notion.site/Running-mev-boost-relay-at-scale-4040ccd5186c425d9a860cbb29bbfe09
   - Chris Hager - Nov 30, 2022
   - Infrastructure notes for running a relay. Critical in understanding all the pieces.
2. Toward an open research and development process for MEV-Boost
   - https://collective.flashbots.net/t/toward-an-open-research-and-development-process-for-mev-boost/464/1
   - Community discussion around the future of mev-boost software.
3. Censorship Resistance: crlists in mev-boost
   - https://github.com/flashbots/mev-boost/issues/215
   - Quintus - July 15, 2022
   - Proposal to add censorship-resistance lists to mev-boost.
4. mev-boost with unconditional payments
   - https://github.com/flashbots/mev-boost/issues/109
   - Alex - April 28, 2022
   - Very early "optimistic-style" mev-boost proposal.
5. how does pos ethereum prevent bribery for late block proposal?
   - https://github.com/flashbots/mev-boost/issues/111
   - Alex - April 28, 2022
   - Very early discussion of timing games implied by outsourcing block construction.
6. The Cost of Resiliance
   - https://writings.flashbots.net/the-cost-of-resilience#:~:text=By%20setting%20the%20minimum%20bid,a%20third%20of%20the%20time.
   - Elaine, Hasu, Alejo - Nov 21, 2022
   - introduces `min-bid` for a heuristic approach to censorship resistance. 
7. MEV-Boost: Merge ready Flashbots Architecture
   - https://ethresear.ch/t/mev-boost-merge-ready-flashbots-architecture/11177 
   - Stephane - Nov 4, 2021

## specific proposals
1. Two-slot proposer/builder separation
   - https://ethresear.ch/t/two-slot-proposer-builder-separation/10980
   - Vitalik - Oct 10, 2021
2. Single-slot PBS using attesters as distributed availability oracle
   - https://ethresear.ch/t/single-slot-pbs-using-attesters-as-distributed-availability-oracle/11877
   - Vitalik - Jan 27, 2022
3. Block vs. Slot Auctions PBS
   - https://mirror.xyz/0x03c29504CEcCa30B93FF5774183a1358D41fbeB1/CPYI91s98cp9zKFkanKs_qotYzw09kWvouaAa9GXBrQ
   - Julian - Dec 14, 2022
4. Burning MEV through block proposer auctions
   - https://ethresear.ch/t/burning-mev-through-block-proposer-auctions/14029
   - Domothy - Oct 26, 2022
5. Committee-driven MEV smoothing
   - https://ethresear.ch/t/committee-driven-mev-smoothing/10408
   - Francesco - Aug 23, 2021
6. Unbundling PBS: Towards protocol-enforced proposer commitments (PEPC)
   - https://ethresear.ch/t/unbundling-pbs-towards-protocol-enforced-proposer-commitments-pepc/13879
   - Barnabe - Oct 8, 2022

## censorship resistance
1. State of research: increasing censorship resistance of transactions under proposer/builder separation (PBS)
   - https://notes.ethereum.org/@vbuterin/pbs_censorship_resistance
   - Vitalik - Jan 29, 2021
2. PBS censorship-resistance alternatives
   - https://notes.ethereum.org/@fradamt/H1TsYRfJc
   - Francesco - Oct 12, 2022
3. Forward inclusion list
   - https://notes.ethereum.org/@fradamt/H1ZqdtrBF
   - Francesco - Nov 15, 2022
4. How much can we constrain builders without bringing back heavy burdens to proposers?
   - https://ethresear.ch/t/how-much-can-we-constrain-builders-without-bringing-back-heavy-burdens-to-proposers/13808
   - Vitalik - Oct 1, 2022
5. Censorship Résistance & PBS (sbc 2022(
   - https://www.youtube.com/watch?v=XZJcZ05d-Wo
   - Justin - Sept 7, 2022

## distributed builders
1. Block-buidler Innovation Post-Merge (sbc 2022)
  - https://www.youtube.com/watch?v=Yx20UUTmgfU
  - Alex - Sept 7, 2022
2. Decentralizing the Builder Role (sbc 2022)
  - https://www.youtube.com/watch?v=fAgrIdyWIqc
  - Vitalik - Sept 7, 2022

## data dashboards

## misc

 
