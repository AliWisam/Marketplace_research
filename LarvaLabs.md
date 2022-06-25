 <!-- Headings -->

# Marketplace Research Document

<br>

## **Contributors** :

<br>

| _Name :_      |         _Email :_          |   _Role :_ |
| :------------ | :------------------------: | ---------: |
| Ehsaan Gondal | *ehsangondal258@gmail.com* | Researcher |

---

<br>

## _Introduction_ :

Larva Labs is a New York-based mobile software firm. They create apps for iOS and Android smartphones. Some of their products’ highlights include the number one paid game on Android, RetroDefense, and a picture manipulation app in the top 50 on iPhone, PhotoTwist.

Two of the most popular projects of Larva Labs besides CryptoPunks are Autoglyphs and Meebits.
CryptoPunks is one of the first Ethereum-based non-fungible tokens. These are algorithmically generated unique digital works of art of 24×24 pixel size. There are only 10,000 unique CryptoPunks. Most of the punks are human characters, i.e., 6039 are males and 3840 are females NFTs. Some special categories like Zombie (88), Ape (24), and Alien (9) are also present. Each of these punks has its page that contains the details about its features, owner, availability status, and transaction history.

---

<br>

## **Dependencies** :

| Parameters :         | Details :                                             |
| -------------------- | ----------------------------------------------------- |
| **Hosting**          | _[vercel](https://vercel.com/pricing)_                |
| **Node.js**          | _[nodejs](https://nodejs.org/en/)_                    |
| **React**            | _[reactjs](https://reactjs.org)_                      |
| **Royalty Registry** | _[Royalty Registry](https://royaltyregistry.xyz/)_    |
| **OpenZeppelin**     | _[OpenZeppelin](https://openzeppelin.com/contracts/)_ |

<br>

<br>

## _Research Parameters_:

<br>

| Parameters :                        | Details :                                                        |
| ----------------------------------- | ---------------------------------------------------------------- |
| **Supported Blockchains :**         | _Ethereum_                                                       |
| **Payment Methods :**               | _Ethereum_                                                       |
| **Creator Fee :**                   | _Percentage: 5%_                                                 |
| **Seller Fee :**                    | _Percentage: 15%_                                                |
| **Royalties :**                     | _Percentage: 10%_                                                |
| **Listing Type/ Selling Methods :** | _Auction ,Sale_                                                  |
| **Categories :**                    | _Art,Photo,Video_                                                |
| **Recommended Wallets :**           | _Metamask,WalletConnect,Coinbase_                                |
| **File Format :**                   | _.JPG,.MP4_                                                      |
| **Max File Size :**                 | _50 Megabyte_                                                    |
| **Media Storage :**                 | _IPFS_                                                           |
| **Ownership :**                     | _non Custodial_                                                  |
| **Licensing :**                     | _Creator must own all legal right: DMCA Title 18, Section 1621._ |
| **KYC :**                           | _Twitter , Instagram_                                            |
| **Community Engagement :**          | _Twitter , Instagram_                                            |

---

<br>

## **Working** :

<br>
Larva Labs established its own marketplace on the CryptoPunks website in addition to developing the CryptoPunks themselves. Users may place bids, purchase, and sell CryptoPunks here. By installing and linking your MetaMask, you may engage with the marketplace. CryptoPunks have also made their way onto OpenSea, a prominent Ethereum-based NFT platform. These pixel punks, on the other hand, are a little different. They’ve been wrapped in ERC-721 tokens, making them tradeable on NFT exchanges.

Purchasing CryptoPunks is a simple process. If you understand how blockchain works, it simply takes a few steps. To learn how it works, follow the step-by-step instructions below.

Purchase Ether: Using a cryptocurrency exchange, you may convert your cash into Ether and transfer it to your wallet.
Transfer it to your wallet: MetaMask is widely used in NFT marketplaces, and CryptoPunks supports it. Create a MetaMask account.
Connect to Larva Labs: You can purchase and sell NFTs from the primary market, Larva Labs, or OpenSea.
Pick a CryptoPunk and Buy It: Take your time looking over the alternatives and then pick a punk.

<br>

## _Marketplace Contracts_ :

<br>

| Contracts : |                                                                Details :                                                                |
| :---------- | :-------------------------------------------------------------------------------------------------------------------------------------: |
|             |
| **Market**  | _[Contract](https://etherscan.io/address/0xcDA72070E455bb31C7690a170224Ce43623d0B6f#code#L1) which allows traders to buy and sell NFTs_ |
|             |

<br>

---

## _Contracts Description_ :

This is a brief overview of the contracts used in Foundation for more detailed information you can use the links given

<br>

<img width="2804" alt="AllPunks" src="https://github.com/larvalabs/cryptopunks/blob/master/punk-variety.png">

## CryptoPunks: Collectible Characters on the Ethereum Blockchain

CryptoPunks are 10,000 unique collectible characters with proof of ownership stored on the Ethereum blockchain. No two are exactly alike, and each one of them can be officially owned by a single person as managed and verified by a contract running on the Ethereum blockchain. You can see which punks are still available along with some more general information over at https://www.larvalabs.com/cryptopunks

This repo contains the Ethereum contract used to manage the Punks, a verifiable image of all the punks, and a unit test to verify the contract's functionality.

### Some Questions

- **How much do the punks cost?** When we first released the project, you could claim a punk by simply paying the transaction fee of around 11 cents. Now, you have to buy a punk from someone else and need to pay the market rate, which at the moment is around 0.3 ETH (~$80 USD). See http://www.larvalabs.com/cryptopunks for the current average price.
- **How much is a punk worth?** Like many things, they're worth whatever someone will pay. People have spent 10 ETH (around $3,000) on the the rarest types.
- **How were the punk images created?** With a generator that was programmed to generate punks with a range of features and rarity. For example, there are only 88 Zombie Punks, 24 Apes, 9 Aliens and exactly [1 Alien Punk smoking a pipe](https://www.larvalabs.com/cryptopunks/details/7804).

### How to Use the CryptoPunks Contract

The easiest way is to use [MyEtherWallet](https://www.myetherwallet.com/#contracts) which has added CryptoPunks to their contract dropdown. If you prefer to use an Ethereum wallet on your computer, the main CryptoPunks contract can be found at address **0xb47e3cd837dDF8e4c57F05d70Ab865de6e193BBB**. Watch this contract in your Ethereum wallet using that address and [this ABI file](/compiled/CryptoPunksMarket.abi).

Once you are watching the contract you can execute the following functions to transact punks:

- `getPunk(uint index)` to claim ownership of a punk (this is no longer useful as all 10,000 punks have been claimed).
- `transferPunk(address to, uint index)` transfer ownership of a punk to someone without requiring any payment.
- `offerPunkForSale(uint punkIndex, uint minSalePriceInWei)` offer one of your punks for sale to anyone willing to pay the minimum price specified (in Wei).
- `offerPunkForSaleToAddress(uint punkIndex, uint minSalePriceInWei, address toAddress)` offer one of your punks for some minumum price, but only to the address specified. Use this to sell a punk to a specific person.
- `enterBidForPunk(uint punkIndex)` enters a bid for the punkIndex specified. Send in the amount of your bid in the value field and we will hold that ether in escrow.
- `acceptBidForPunk(uint punkIndex, uint minPrice)` to accept a pending bid for the specified punk. You can specify a minPrice in Wei to protect yourself from someone switching the bid for a lower bid.
- `withdrawBidForPunk(uint punkIndex)` will withdraw a bid for the specified punk and send you the ether from the bid.
- `buyPunk(uint punkIndex)` buy punk at the specified index. That punk needs to be previously offered for sale, and you need to have sent at least the amount of Ether specified as the sale price for the punk.
- `withdraw()` claim all the Ether people have previously sent to buy your punks.

### Verifying the Punks are 100% Authentic and Legit CryptoPunks™

<img width="2804" alt="All Punks" src="https://github.com/larvalabs/cryptopunks/raw/master/punks.png">
This is the official and genuine image of all of the CryptoPunks that have been created. To allow verification that the punks being managed by the CryptoPunks Ethereum contract are the same as what you see in the image, we have embedded a SHA256 hash of the image file into the contract. You can generate this hash for the punks image file via a command line similar to `openssl sha -sha256 punks.png` and compare that to the embedded hash in the contract `ac39af4793119ee46bbff351d8cb6b5f23da60222126add4268e261199a2921b`.

---

<br>

## _Sources :_

<br>

- [larvalabs.com](https://www.larvalabs.com)
- [medium.com](https://medium.com/thedapplist/what-are-cryptopunks-a7428e0fd6e6)

<br>

---

<br>

## _Resources_:

<br>

- [NFT Recourses](https://github.com/gianni-dalerta/awesome-nft)
- [Marketplaces Sheet](https://docs.google.com/spreadsheets/d/1Q_6GnX7DhFDBD4hHKaMUkesMIO9rxJx5ewcKVv4Tjag/edit)
