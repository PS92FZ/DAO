# Minimal Cosmos Hub

Bitcoin does one thing well, it reliably transfers value between parties. This
was Bitcoin’s original purpose, and it remains its focus; the Bitcoin
community’s commitment to defending this simple protocol helps maintain its
success.  The one thing Bitcoin doesn't do well is scaling,
and while the Lightning Network solves many problems, it isn't a general
solution for Bitcoin scaling, the "holy grail" of crypto.

If the Cosmos Hub had to do one thing well, it would be multi-token IBC
pegging. But the Cosmos Hub isn't Bitcoin (which can still function without
general scaling); it wants a business model to stay economically strong, and
it just so happens to have one already that we are in alignment with, and one
that happens to solve the scaling problem as well -- interchain security, or 
ICS. _NOTE: I'm only referring to ICS1, also known as Simple Replicated 
Security, which includes all protocols where the validator set is simply 
replicated across multiple blockchains and slash conditions are always 
submitted to a root chain._

The base economic model for the ATOM token is earning transaction fees across
all the ICS hosted zones. While it may or may not be true that Bitcoin can
sustain its security model with only transaction fees in the future when block
rewards to go zero, it certainly would be true for the Cosmos Hub with ICS. 
For one, cost of attack of PoW is very different than PoS; the cost to attack 
PoW discounting mining infrastructure is rather minimal (just six blocks worth
of inflation+fees in Bitcoin) whereas in the Cosmos Hub with Tendermint BFT, 
the cost of slashing is not just the inflation+fees of one or few blocks, but
rather always at least 1/3 of the total staked ATOMs.

The killer application to be scaled via ICS is, besides simple token
transfers, most likely to be a smart contract platform. Whether it be 
Solidity, CosmWASM, WASM, Gno, or something else, the expressivity and 
simplicity of smart contract programming is theoretically unparalleled
(as compared to direct application programming via say the Cosmos SDK), and
is practically proven somewhat with the Solidity programming language, and 
completely with Gno. _NOTE: Gno will be free software, see 
https://github.com/gnolang/gno/pull/397_

Between IBC token pegging, ICS scaling, and killer applications, especially
smart contract applications secured by ICS with the Cosmos Hub validators,
there's no doubt that the Cosmos Hub will attract customers in the form of
both end users (for simple token transfers and smart contracts) as well as
independent blockchains (zones) that want the functionality of a token hub.

That is, if zones want a token hub. Presently, many Cosmos chains IBC connect
to many other chains. But this isn't a sustainable model, and eventually the
ecosystem will come to understand better the need for hubs and zones. To
demonstrate, say there are 10,000 zones. Say a zone fails and it requires
manual intervention. With 10,000 IBC connections you require 10,000 zones to
all agree on recovery procedure, which will never happen. But a zone connected
to a more secure hub will be protected when it needs intervention.

Regarding gno.land, because that's the smart contract system I've been working
on, we plan to IBC connect to one token hub. I see the hub as a kind of
Depository Trust & Clearing Corporation (DTCC). Where tokens are being
exchanged from zone AAA to zone BBB, they are actually pegged on zone
COSMOSHUB and AAA and BBB work on representations of the tokens. Zones AAA and
BBB chose to do so because AAA and BBB want the convenience, security, 
availability, scalability, and programmability that the CosmosHub offers. Of
course, we are free today to use paper shares, but (there's a word for this,
"holder xxx"?) there are many reasons to "dematerialize" them. The same will 
be true for zone tokens. We must have hubs and spokes. What we need is freedom
of choice of hubs.


# Tokenomics

Remove the minimum inflation bounds of 7%, and also allow the inflation rate
to go negative if there are too many ATOMs bonded.

We highly recommend ditching the MintTx feature, and only using the tax pool
as a matter of principle, to use a LoTR analogy, to throw the ring into the 
fire. Instead, we focus on creating tooling to responsibly consume our budget
allocation.

This naturally leads to the need for DAOs for accountable treasury management.

See [Prop88](https://www.mintscan.io/cosmos/proposals/88) for a proposal to
increase the tax rate for the community pool.


# Liquid Staking

Get rid of liquid staking, specifically on the Cosmos Hub, entirely.


# Governance

Yes/No/NoWithVeto should just be Yes/No with +2/3 required for all approvals.
Some proposal types by constitution may require more than +2/3 to adopt, such
as parameter update proposals that may be dangerous or contentious. This
removes the complexity of needing the veto system.
[Prop75](https://www.mintscan.io/cosmos/proposals/75) should also be reverted.

Also, the governance process should extend the voting deadline to ensure at
least 2 weeks of voting after the minimum quorum has been met. If anything,
the total voting period should be longer for normal proposals, to enable 
longer deliberation.


# Tendermint & Cosmos SDK & Forks

## Tendermint*

* The usage of "Tendermint" to refer to software is deprecated.
* "github.com/tendermint/tendermint" --> freeze at latest release for cosmoshub-4.
* [github.com/tendermint/tendermint2](Tendermint2) --> new branch led by
NewTendermint,LLC.

For Tendermint and CosmosSDK forks, please fill out the [survey form](https://docs.google.com/forms/d/e/1FAIpQLSeAZ4ILjJL39Fk_LIZD0L5qvFt4mqONVPaQ-ODuFSF0-dx4hw/viewform?usp=sf_link). 

## Interbranch Dev Team (IDT)

Inter-branch development team as a DAO managed & funded development team,
seperate from the Gaia development team.

Will work with Tendermint2 and other forks, as well as
CosmosSDK, and other forks, to create a directory/taxonomy of forks.

Will suggest PRs between Tendermint, Tendermint2, the CosmosSDK, and the
next
favorite SDK version, as well as however team members want.

Will work with the declared principles of each repo, such as dependency
reduction for Tendermint2.

Will solve ICS separately from any other team, for diversity's sake.

Funding commitment TBD from AIB, but will be significant. ICF should match.

The IDT is separate from but intersects with many other development teams.

## The People's Forum for Cosmos & Crypto

All in Bits, Inc will help steer this forum to bring Cosmos and interchain
ecosystem together, starting with the forks around Tendermint and the Cosmos
SDK. In this way, AIB will not just be partially funding, but helping the
Interbranch Dev Team connect with every developer and project.


# Constitution

What would make a good token hub? Besides adoption, what zones want is
security. Not just economic security in the form of a high market cap for the
staking token, but also security in the form of conservatism, in the form of
not taking unnecessary risks. Prop82 was the kind of proposal that would turn
the hub from something minimal and secure into something that is risky and
unproven. To prevent similar situations from happening repeatedly, we need
among other things, a written constitution that declares the scope of the
Cosmos Hub. A constitution document isn't sufficient, but it is necessary to
retain focus and culture.

We need multiple ground-up approaches here, and synthesis of ideas, before we
can come up with the final product.

We recommend that we use this repository to keep track of all constitution
efforts, so that they may perhaps merge into one.

 * https://github.com/tendermint/atom_one

NOTE: The ATOM ONE constitution proposal needs to split into two pieces. The
core constitution, and the secondary amendment that discusses ICS2 and the
PHOTON token.

NOTE: an english constitution is a superset of the major procedures of
the governance module. It doesn't need to include all of the elements, but it
needs to include enough so that when there is any doubt, it can serve as
arbiter. For example, if there was a software bug, the constitution may
elucidate what was intended, in plain english. Thus, the ATOM ONE constitution
still lacks much of the governance features that are already implemented.


# Resources

 * https://github.com/tendermint/ecosystem
 * https://github.com/tendermint/tendermint2
 * https://github.com/tendermint/atom_one
 * https://www.mintscan.io/cosmos/proposals/88 - Proposal to increase the
community pool tax rate
