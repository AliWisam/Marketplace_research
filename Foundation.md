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

The Foundation marketplace is a contract which allows traders to buy and sell NFTs. Previously (the code on mainnet) supported just Auctions and Private Sales. This upcoming launch adds Buy Price and Offers.

- Auctions last for 24 hours. The NFT is escrowed in the market contract when it's listed. As soon as a bid is received the NFT cannot be withdrawn, guaranteeing that the sale will go through and the highest bidder gets the NFT. If a bid is placed in the final minutes of an auction, the countdown timer resets to 15-minutes remaining.
- Private Sales use a EIP-712 signature from the seller to authorize the trade to a specific buyer / price point. The buyer has 24 hours to accept the offer to buy the NFT before the signature expires.
- Buy Price allows the owner of an NFT to list it for sale at a specific price point. The NFT is escrowed in the market contract when the price is set. Once a collector buys at the price set, the NFT is instantly transferred and revenue is distributed.
- Offers allow collectors to make an offer for an NFT. The seller has 24-25 hours to accept the offer. During this time, the collector's funds are locked in the FETH ERC-20 contract - ensuring that an offer remains valid until its expiration. If a higher offer is made, the original user's FETH balance is unlocked and they can use those funds elsewhere (or withdraw the ETH).

All sales in the Foundation market will pay the creator 10% royalties on secondary sales. This is not specific to NFTs minted on Foundation, it should work for any NFT. If royalty information was not defined when the NFT was originally deployed, it may be added using the [Royalty Registry](https://royaltyregistry.xyz/) which will be respected by market contract
<br>

## _Research Parameters_:

<br>

| Parameters :                        | Details :                        |
| ----------------------------------- | -------------------------------- |
| **Supported Blockchains :**         | _Ethereum_ |
| **Payment Methods :**               | _Ethereum_ |
| **Buyer Fee :**                     | _Percentage:0%_ |
| **Seller Fee :**                    | _Percentage:5% |
| **Royalties :**                     | _Percentage:10%_ |
| **Listing Type/ Selling Methods :** | _lorem ipsum,lorem ipsum,_       |
| **Categories :**                    | _Art,Photo,Video_ |
| **Recommended Wallets :**           | _Metamask,WalletConnect,Coinbase_ |
| **File Format :**                   | _.JPG,.MP4,Video_ |
| **Max File Size :**                 | _50 Megabyte_       |
| **Media Storage :**                 | _IPFS_   |
| **Decentralization :**              | _lorem ipsum,lorem ipsum,_       |
| **Protocol Supported :**            | _lorem ipsum,lorem ipsum,_       |
| **Ownership :**                     | _lorem ipsum,lorem ipsum,_       |
| **Licensing :**                     | _lorem ipsum,lorem ipsum,_       |
| **Governance :**                    | _lorem ipsum,lorem ipsum,_       |
| **Staking :**                       | _lorem ipsum,lorem ipsum,_       |
| **KYC :**                           | _Twitter,Instagram |
| **Regulation :**                    | _lorem ipsum,lorem ipsum,_       |
| **Company Registration :**          | _lorem ipsum,lorem ipsum,_       |
| **Community Engagement :**          | _lorem ipsum,lorem ipsum,_       |

---

<br>

## _Marketplace Contracts_ :

<br>

| Contracts :             |         Details :          |
| :---------------------- | :------------------------: |
| **Minting NFT**         | _lorem ipsum, lorem ipsum_ |
| **Buying Process**      | _lorem ipsum, lorem ipsum_ |
| **Order Booking**       | _lorem ipsum, lorem ipsum_ |
| **Funcds Distribution** | _lorem ipsum, lorem ipsum_ |

<br>

---

<br>

## _Description for Parameters_ :

<br>

- **Supported Blockchains :**

  - [Ethereum](https://ethereum.org/en/)
  - [Polygon](https://polygon.technology/)

  <br>

- **_Payment Methods :_**

  -
  - <br>

- **_Buyer Fee :_**

  -
  -

  <br>

- **_Seller Fee :_**

  -
  - <br>

- **_Royalties :_**

  -
  - <br>

- **_Listing Type/ Selling Methods :_**

  -
  - <br>

- **_Categories :_**

  -
  - <br>

- **_Recommended Wallets :_**

  -
  - <br>

- **_File Format :_**

  -
  - <br>

- **_Max File Size :_**

  -
  - <br>

- **_Media Storage :_**

  -
  - <br>

- **_Decentralization :_**

  -
  - <br>

- **_Protocol Supported :_**

  -
  - <br>

- **_Ownership :_**

  -
  - <br>

- **_Licensing :_**

  -
  - <br>

- **_Governance :_**

  -
  - <br>

- **_Staking :_**

  -
  - <br>

- **_KYC :_**

  -
  - <br>

- **_Regulation :_**

  -
  - <br>

- **_Company Registration :_**

  -
  - <br>

- **_Community Engagement :_**

  -
  -

---

<br>

## _Contracts Description_ :

<br>

- **_Minting NFT :_**

  -
  -

<br>

```javascript
function mint() {
  return "Congrats! You got your first NFT";
}
```

<br>

- **_Buying Process :_**

  -
  -

<br>

```javascript
function buy() {
  return "Congrats! You bought NFT for 1 ETH";
}
```

<br>

- **_Order Booking :_**

  -
  -

<br>

```javascript
function fillOrder() {
  return "Order Filled";
}
```

<br>

- **_Funds Distribution :_**

  -
  -

<br>

```javascript
function distribute() {
  return "Funds distributed sucesfuly";
}
```

---

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
