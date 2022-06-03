 <!-- Headings -->

# Marketplace Research Document

<br>

## **Team** :

<br>

| _Name :_                |        _Email :_         | _Role :_ |
| :----------------- | :--------------------------: | -------------: |
| _Ali Wisam_        | *raliwisaam73@gmail.com*     |  Team Leader   |
| _Burhan Saleemi_   | *burhansaleemi@tutanota.com* |  Researcher    |
| _Ruwaifa Tahir_    | *ruwaifatahir@gmail.com*     |  Repository    |

---

<br>

## _Introduction_ :

The Foundation claims to be web3 destination. Is actuality a NFT marketplace which was invite only in its beginning (by geting high profile colerctors like [PleasrDAO](https://pleasr.org#) creaters or NFT for [tor](https://www.torproject.org) and [Edward Snowden](https://foundation.app/@Snowden))made it self a premium/trustable
reputationthrough with it still 
distinguishes it self and charges its users 5% fee with is double the fee of other marketplaces.

<br>

## _Research Parameters_:

<br>

| Parameters :                        | Details :                        |
| ----------------------------------- | -------------------------------- |
| **Supported Blockchains :**         | _Ethereum_ |
| **Payment Methods :**               | _Ethereum_ |
| **Buyer Fee :**                     | _Percentage: 0%_ |
| **Seller Fee :**                    | _Percentage: 5%_ |
| **Royalties :**                     | _Percentage: 10%_ |
| **Listing Type/ Selling Methods :** | _lorem ipsum,lorem ipsum,_       |
| **Categories :**                    | _Art,Photo,Video_ |
| **Recommended Wallets :**           | _Metamask,WalletConnect,Coinbase_ |
| **File Format :**                   | _.JPG,.MP4_ |
| **Max File Size :**                 | _50 Megabyte_       |
| **Media Storage :**                 | _IPFS_   |
| **Decentralization :**              | _lorem ipsum,lorem ipsum,_       |
| **Protocol Supported :**            | _lorem ipsum,lorem ipsum,_       |
| **Ownership :**                     | _lorem ipsum,lorem ipsum,_       |
| **Licensing :**                     | _lorem ipsum,lorem ipsum,_       |
| **Governance :**                    | _lorem ipsum,lorem ipsum,_       |
| **Staking :**                       | _lorem ipsum,lorem ipsum,_       |
| **KYC :**                           | _Twitter,Instagram_ |
| **Regulation :**                    | _lorem ipsum,lorem ipsum,_       |
| **Company Registration :**          | _lorem ipsum,lorem ipsum,_       |
| **Community Engagement :**          | _lorem ipsum,lorem ipsum,_       |

---
<br>
- Auctions last for 24 hours. The NFT is escrowed in the market contract when it's listed. As soon as a bid is received the NFT cannot be withdrawn, guaranteeing that the sale will go through and the highest bidder gets the NFT. If a bid is placed in the final minutes of an auction, the countdown timer resets to 15-minutes remaining.
- Private Sales use a EIP-712 signature from the seller to authorize the trade to a specific buyer / price point. The buyer has 24 hours to accept the offer to buy the NFT before the signature expires.
- Buy Price allows the owner of an NFT to list it for sale at a specific price point. The NFT is escrowed in the market contract when the price is set. Once a collector buys at the price set, the NFT is instantly transferred and revenue is distributed.
- Offers allow collectors to make an offer for an NFT. The seller has 24-25 hours to accept the offer. During this time, the collector's funds are locked in the FETH ERC-20 contract - ensuring that an offer remains valid until its expiration. If a higher offer is made, the original user's FETH balance is unlocked and they can use those funds elsewhere (or withdraw the ETH).

All sales in the Foundation market will pay the creator 10% royalties on secondary sales. This is not specific to NFTs minted on Foundation, it should work for any NFT. If royalty information was not defined when the NFT was originally deployed, it may be added using the [Royalty Registry](https://royaltyregistry.xyz/) which will be respected by market contract

## Marketplace State Machine

Below is a diagram depicting the marketplace states and transitions for the various market tools.

<img width="5522" alt="MarketplaceStateMachine" src="https://user-images.githubusercontent.com/14855515/155433938-428f475f-2c6d-441f-9502-674d0f7953fc.png">






<br>

## _Marketplace Contracts_ :

<br>

| Contracts :             |         Details :          |
| :---------------------- | :------------------------: |
| **FETH**                  | _[ERC-20 token](https://eips.ethereum.org/EIPS/eip-20) modeled after [WETH9](https://etherscan.io/address/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2#code)_ |
| **Market**                | _[Contract](/docs/FNDNFTMarket.md) which allows traders to buy and sell NFTs_ |
| **OpenZeppelin Contracts**| _Dependencie [OpenZeppelin Contracts](https://openzeppelin.com/contracts/)_ |
| **Royalty Registry**      | _Dependencie [Royalty Registry](https://royaltyregistry.xyz/)_ |

<br>

---

## _Contracts Description_ :

<br>

## Contract UML

Below is a diagram depicting the relationships between various contracts.

<img width="2804" alt="UMLContractDiagram" src="https://user-images.githubusercontent.com/14855515/155433971-d048e5dc-86dc-49fd-8c0e-b930117867c5.png">

## FETH ERC-20 token

FETH is an [ERC-20 token](https://eips.ethereum.org/EIPS/eip-20) modeled after [WETH9](https://etherscan.io/address/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2#code). It has the added ability to lockup tokens for 24-25 hours - during this time they may not be transferred or withdrawn, except by our market contract which requested the lockup in the first place.

We strive to offer strong guarantees for both buyers and sellers, this is why a seller cannot back out of an auction once the first bid has been placed.

For making offers, this means once a collector has made an offer for an NFT - those funds must remain available for a period of time so the seller has a reasonable window to consider and accept it without worrying that the collector might just withdraw their funds, making the offer invalid.

We implement this feature in the FETH token contract, allowing funds to be locked up for 24-25 hours while the seller considers accepting the offer.

Once the offer expires, the FETH tokens become available again. Their `balanceOf` automatically increases at the time it expires and they can then transfer or withdraw those funds -- or they can use them to place another offer!

Since after lockups expire, FETH is just another wrapped ETH token contract - we allow using your available FETH balance with all the other market tools: place a bid with FETH, buy now with FETH, or buy from a private sale using FETH.

## Market Tool Interactions

Each of the market tools have dependencies and interactions with the others. The goal of these interactions is to do what's most likely intended or expected by the user -- and avoid leaving either the buyer or seller in an awkward state. For instance:

- In progress auctions must go to the highest bidder. This means that a buy price is not valid, it cannot be accepted. And since both offers and auctions last for 24 hours, the offer cannot be accepted so we should free those FETH tokens for the collector to use elsewhere.
- Auto-buy: If you make an offer above the current buy now price, process the purchase immediately.
- Auto-accept-offer: Similarly if you set a buy price lower than the highest offer, accept that offer instead.

It's easy to reach 100% code coverage, but much harder to know all these interactions work the way users will expect them too. Feedback along these lines is in scope for this contest.



- **_placeBid:_**

<br>

```solidity
function placeBid(uint256 auctionId) external payable
```

<br>

Place a bid in an auction. A bidder may place a bid which is at least the value defined by `getMinBidAmount`. If this is the first bid on the auction, the countdown will begin. If there is already an outstanding bid, the previous bidder will be refunded at this time and if the bid is placed in the final moments of the auction, the countdown may be extended.



- **_Buy :_**
<br>

```javascript
solidity
function buy(address nftContract, uint256 tokenId, uint256 maxPrice) external payable
}
```

<br>
Buy the NFT at the set buy price. `msg.value` must be &lt;= `maxPrice` and any delta will be taken from the account&#39;s available FETH balance.

_`maxPrice` protects the buyer in case a the price is increased but allows the transaction to continue when the price is reduced (and any surplus funds provided are refunded)._
  



- **_acceptOffer :_**
- 
<br>

```javascript
ffunction acceptOffer(address nftContract, uint256 tokenId, address offerFrom, uint256 minAmount) external nonpayable
}
```

<br>

Accept the highest offer for an NFT.

_The offer must not be expired and the NFT owned + approved by the seller or available in the market contract&#39;s escrow._

- **_makeOffer:_**

<br>

```javascript
function makeOffer(address nftContract, uint256 tokenId, uint256 amount) external payable returns (uint256 expiration)
```

---

Make an offer for any NFT which is valid for 24-25 hours. The funds will be locked in the FETH token contract and become available once the offer is outbid or has expired.

_An offer may be made for an NFT before it is minted, although we generally not recommend you do that. If there is a buy price set at this price or lower, that will be accepted instead of making an offer. `msg.value` must be &lt;= `amount` and any delta will be taken from the account&#39;s available FETH balance._

<br>

## _Conclusion_ :

-
-
-

<br>

---

<br>

## _Contributors_ :

-
-
-

<br>

---

<br>

## _Sources :_

<br>

-
-

<br>

---

<br>

## _Resources_:

<br>

- [NFT Recourses](https://github.com/gianni-dalerta/awesome-nft)
- [Marketplaces Sheet](https://docs.google.com/spreadsheets/d/1Q_6GnX7DhFDBD4hHKaMUkesMIO9rxJx5ewcKVv4Tjag/edit) 
