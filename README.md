# What
Tokenize professional services billed on hourly based where value can be bartered, used to create derivatives, and otherwise utilized in a decentralized manner.

An example of such tokenization is ConsenSys' TURN NFTs (Time-Unit Representative NFTs) where the tokens are sold at a flat rate and can be redeemed for the service they represent.

Such tokens circulating freely on the market are a gateway to market price **discovery**, where the demand and the price action are consistent with the demand for the corresponding service and its booking rates. ConsenSys even threw in an auction/bidding mechanism.

However, TURN tokens are conceptually limited to a single service provider, and while every other service provider is free to deploy their own version of this, the associated financial and time investments may not be worth it for every service provider. In addition, the business logic would naturally vary from one service provider to another as minor adjustments are made, and consequential errors could be introduced into the code.

While it could be reasoned that this is not a deterrent in any way, and, in fact, it is the way of Web3 to _let a hundred flowers bloom; let a hundred schools of thought contend_, consider also, as I do, that a uniform, consistent protocol for tokenizing services could itself be a building block for something much larger.

Two readily apparent use-cases where consistency and uniformity come in handy:
1) A DAO that funds a project where multiple professionals are involved. (Like Pipeline DAO.)
2) Finding and hiring several professionals in a decentralized manner to work on a traditionally structured project.

Consider as well that a non-uniform set of tokens will probably prevent convenient bartering.

## Why Not a Traditional Web App?
1) Onboarding is painful, gotta jump through lots of hoops. The friction could be avoided.
2) Diversity prevents unification. See https://xkcd.com/927/ on Standards. A protocol style token, such as proposed here, could be used directly by all platforms and also leaves room and flexibility for building upon it further.
3) Decentralized tech with its ebb and flow provides a perfect exchange medium that could stand the test of time, similarly to DEXes.

# Why
1. It's a building block for much larger systems. We need to standardize the way services are tokenized and consumed.
2. It's an on-chain reputation system that is largely based on an internal feedback loop (token consumption rate, POAP, customer reviews). Not entirely immune from manipulation, but good enough as a jumping off point.
3. It's the inevitable future of digital services billed hourly.

Note. Per-project quotes _should_ be based on estimating the number of hours that goes into a project, and it's up to the service provider to ideally aim for a precise estimation based on their discussions with the client. It could be argued there are cases when a per-project quote does not match the number of hours spent, but it can _always_ be expressed in a number of hours at a certain hourly rate.

# How
The Promise of Work Token is an ERC721 compatible token extended with features borrowed from ERC1155 and ERC3525 and using implementation ideas from both ERC721A and ERC3525. Note: No gas golfing.

# Features
- On-chain token visualization (via SVG.) All the tokens have a similar design to ensure consistency and rapid recognition.
- Optimized bulk minting.
- Optimized bulk transfers + batch transfers.
- Built-in fractionalization.
- Value transfer between tokens.
- Arbitrary time units (down to a second precision).
- Per-token escrow (funds released to the service provider and tokens are burned when work is delivered).
- Built-in swapping via the stable token used to settle (defaults to system-wide USDT).
- Forced Buy-backs (tokens can be sold back at any time at the original price).
- Dynamic minting caps and pricing (set by the service provider).
