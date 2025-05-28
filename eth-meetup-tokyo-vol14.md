---
routerMode: hash
# You can also start simply with 'default'
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
# background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: EIP-7702, x402 and Future Prospects of Crypto UX
titleTemplate: '%s'
# info: |
#   ## Slidev Starter Template
#   Presentation slides for developers.

#   Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# open graph
# seoMeta:
#  ogImage: https://cover.sli.dev
fonts:
  sans: Nunito
  serif: Arvo
  mono: IBM Plex Mono
  title: Raleway
  dot: DotGothic16
  weights: 400, 700
  italic: true
seoMeta:
  ogTitle: EIP-7702, x402 and Future Prospects of Crypto UX
  ogDescription: Slide at Ethereum Meetup Tokyo Vol.14
  ogImage: https://yujiym.github.io/slides/eth-meetup-tokyo-vol14/assets/14/ogp.png
  ogUrl: https://yujiym.github.io/slides/eth-meetup-tokyo-vol14
  twitterCard: summary_large_image
  twitterTitle: EIP-7702, x402 and Future Prospects of Crypto UX
  twitterDescription: Slide at Ethereum Meetup Tokyo Vol.14
  twitterImage: https://yujiym.github.io/slides/eth-meetup-tokyo-vol14/assets/14/ogp.png
layout: intro
---

# <span class="marker blue">EIP-7702</span>, <span class="marker green">x402</span> and <br>Future Prospects of <LineShadowText>Crypto</LineShadowText> <LineShadowText><span class="marker pink">UX</span></LineShadowText>

<div class="abs-br m-6 text-gray-400"><a href="https://lu.ma/188zc6f5" rel="noreferrer" target="_blank">Ethereum Meetup Tokyo Vol.14</a>
</div>

---
layout: image-left
image: /assets/14/pectra-summary.webp
---

#### Post Pectra{class="font-serif"}

<blockquote class="small mt-2">

- __[EOF (Ethereum Object Format)](https://eips.ethereum.org/EIPS/eip-7692)__: Extensible and versioned container format for EVM bytecode, reducing deployment costs, and better optimization of contract execution.
- __[EIP-7594](https://eips.ethereum.org/EIPS/eip-7594)__: Focuses on creating a distributed system (PeerDAS) for Layer 2 data availability, but it was deemed too complex to include in Pectra.
- __[Verkle Trees](https://ethereum.org/en/roadmap/verkle-trees/)__: Adds a more compact and efficient data structure to replace Merkle trees, enabling stateless Ethereum clients, reducing the storage for validators.
- __[EIP-7623](https://eips.ethereum.org/EIPS/eip-7623)__: Proposes higher calldata costs for rollups to incentivize the use of blobs for off-chain data storage, which improves scalability but may temporarily increase fees for L2s.
- __[EIP-7782](https://eips.ethereum.org/EIPS/eip-7782)__: Reduces Ethereum's slot time to optimize block finalization speed and transaction throughput, but demands careful testing to avoid compromising network stability.
- __[EIP-7783](https://eips.ethereum.org/EIPS/eip-7783)__: Gradual increases to gas limits, allowing the network to handle higher transaction volumes over time, but requires further evaluation on centralization and hardware constraints.
</blockquote>

<p class="links">🔗<a href="https://www.datawallet.com/crypto/ethereum-pectra-upgrade-explained" target="_blank" rel="noreferrer">Ethereum Pectra Upgrade & EIPs Explained | Datawallet</a></p>

---

# 🧐 What is EIP-7702

> EIP-7702 is a proposal to add a new Transaction type to allow an EOA to designate a Smart Contract as its "implementation".<br>
> The main difference between an EIP-7702 Transaction and other transactions is the inclusion of a "authorization list" property, a set of `(chain_id, contract_address, nonce, y_parity, r, s)` tuples that depict what Contracts should be delegated onto the Externally Owned Account.

> Applications of EIP-7702 include:
> - __Batching__: allowing multiple operations from the same user in one atomic transaction. One common example is an ERC-20 approval followed by spending that approval, a common workflow in DEXes that requires two transactions today. Advanced use cases of batching occasionally involve dependencies: the output of the first operation is part of the input to the second operation.
> - __Sponsorship__: account X pays for a transaction on behalf of account Y. Account X could be paid in some other ERC-20 for this service, or it could be an application operator including the transactions of its users for free.
> - __Privilege de-escalation__: users can sign sub-keys, and give them specific permissions that are much weaker than global access to the account. For example, you could imagine a permission to spend ERC-20 tokens but not ETH, or to spend up to 1% of total balance per day, or to interact only with a specific application.

<p class="links">🔗<a href="https://viem.sh/docs/eip7702" target="_blank" rel="noreferrer">EIP-7702 Overview | viem</a></p>

---

# ⏱️ EIP-7702 at the moment

From ZeroDev's posts:

> ##### **The Adoption Cycle**
> - **Standalone wallets (e.g. MetaMask)** will implement support for 7702 but require users to opt in.
> - **Embedded wallets (e.g. privy/dynamic)** will also implement support for 7702, but require developers to opt in.
> - **Innovative dapps** will implement AA features using 7702-enabled embedded wallets.
> - **Adventurous EOA users** will try these dapps by turn on 7702 for their standalone wallets.
> - Seeing more users turning on 7702 and more dapps adopting 7702, the slower-moving dapps will start leveraging 7702/AA too.
> - As the number of AA-enabled dapps grow, the slower-moving users will enable 7702 too, in order to not miss out on all the new apps and new experiences.
> - As more and more users enable 7702, the long-tail of wallets who are yet to support 7702 will be forced to add support or risk fading into irrelevancy.

> ##### **DApp Developers**
> - **Open DApps (e.g. Uniswap/AAVE)** detect smart wallet (EIP-5792), adopting features with capabilities.
> - **Closed DApps (e.g. MetaMask/Infinex/DeFi.app)** : have choice between adopting smart account ot EIP-7702 account(smart EOAs).

<p class="links">🔗<a href="https://docs.zerodev.app/blog/7702-adoption" target="_blank" rel="noreferrer">What does EIP-7702 mean for YOU? Part 1 -- The Adoption Cycle of 7702</a>, <span class="mr-2" />🔗<a href="https://docs.zerodev.app/blog/7702-for-dapps" target="_blank" rel="noreferrer">Part 2 -- DApp Developers</a></p>

---

<div class="grid grid-cols-4 gap-4">
  <Tweet id="1920117837554733502" scale="0.7" />
  <Tweet id="1925116235064254772" scale="0.7" />
</div>

<iframe src="https://support.metamask.io/configure/accounts/switch-to-or-revert-from-a-smart-account/" class="w-1/2 h-full absolute right-0 top-0" loading="eager" />
<p class="links">🔗<a href="https://support.metamask.io/configure/accounts/switch-to-or-revert-from-a-smart-account/">How to switch to or revert from a smart account</a></p>

---

<iframe src="https://swiss-knife.xyz/7702beat" class="w-full h-full absolute right-0 top-0"
  loading="eager"
/>

<p class="links z-10">🔗<a href="https://swiss-knife.xyz/7702beat">7702 Beat</a></p>

---

# Porto + Account

<div class="w-5/8">

- EIP-7702 based smart account, Multisig?
  - [PortoAccount.sol](https://github.com/ithacaxyz/account/blob/main/src/PortoAccount.sol)
    - A keychain that holds user funds, enforces permissions via Keys, manages nonces to prevent replay attacks, and enables secure executions from the account
  - [Orchestrator.sol](https://github.com/ithacaxyz/account/blob/main/src/Orchestrator.sol)
    - The Orchestrator is a privileged contract that facilitates trustless interactions between the relay and the account.
- Opening iframe dialog: `https://stg.id.porto.sh/`
  - Passkeys: Per domain authorization, Stored in user's secure enclave, dApps cannot determine whether an account already exists. (Signup or Signin) -> improved with app Session

</div>

<div class="bg-[url(/assets/14/porto-features.png)] absolute h-full top-0 right-0 w-3/8 bg-contain bg-no-repeat" />
<p class="links z-10">🔗<a href="https://porto.sh/">porto.sh</a></p>

---

# Porto + Account

> All-in-one EIP-7702 powered account contract, coupled with Porto<br>
> Every app needs an account, traditionally requiring separate services for auth, payments, and recovery. Doing this in a way that empowers users with control over their funds and their data is the core challenge of the crypto space. While crypto wallets have made great strides, users still face a fragmented experience - juggling private keys, managing account balances across networks, having to install browser extensions, and more.<br>
> We believe that unstoppable crypto-powered accounts should be excellent throughout a user's journey:

<blockquote class="small">

#### Features out of the box

- [x] Secure Login: Using WebAuthN-compatible credentials like PassKeys.
- [x] Call Batching: Send multiple calls in 1.
- [x] Gas Sponsorship: Allow anyone to pay for your fees in any ERC20 or ETH.
- [x] Access Control: Whitelist receivers, function selectors and arguments.
- [x] Session Keys: Allow transactions without confirmations if they pass low-security access control policies.
- [ ] Multi-factor Authentication: If a call is outside of a certain access control policy, require multiple signatures.
- [ ] Optimized for L2: Using BLS signatures.
- [ ] Chain Abstraction: Transaction on any chain invisibly. Powered by ERC7683. WIP
- [ ] Privacy: Using stealth addresses and confidential transactions.
- [ ] Account Recovery & Identity: Using ZK (Email, OAUth, Passport) and more.
</blockquote>

<p class="links z-10">🔗<a href="https://github.com/ithacaxyz/account?tab=readme-ov-file#features-out-of-the-box" taeget="_blank" rel="noreferrer">Accoout | ithaca.xyz</a></p>


---

# Gelato EIP-7702 DEMO implatation

- 👀 Please check articles

<p class="links z-10">🔗<a href="https://mirror.xyz/0xtomo.eth/lHXc3RyTDrszpgRxxCOMYTLIWqEj4xtWJH5_DEwyIag">EIP-7702凄すぎ説 — 0xtomo</a>, 🔗<a href="https://github.com/gelatodigital/gelato-eip-7702-demo/">gelatodigital/gelato-eip-7702-demo
</a></p>

---

# Smart Wallets (Coinbase)

<div class="w-2/3 pr-6">

- ERC-4337 based Smart Account (No EIP-7702)
  - [CoinbaseSmartWallet.sol](https://github.com/coinbase/smart-wallet/blob/main/src/CoinbaseSmartWallet.sol)
- Multiple Owners: Passkey owners and Ethereum address owners
  - [MultiOwnable.sol](https://github.com/coinbase/smart-wallet/blob/main/src/MultiOwnable.sol)
- Opening popup window: `https://keys.coinbase.com/`
- Cross-chain replayability for owner updates and other actions: sign once, update everywhere.
</div>

<img src="/assets/14/onchainkit-wallet.png" class="w-1/3 h-full absolute right-0 top-0"
  loading="eager"
/>

<p class="links z-10">🔗<a href="https://wallet.coinbase.com/smart-wallet">Coinbase Wallet</a></p>

---


# What is x402

<div class="w-9/16 text-xs relative h-full">
<blockquote class="small mr-8">
<p class="text-sm">Built around the HTTP 402 status code, x402 enables users to pay for resources via API without registration, emails, OAuth, or complex signatures.</p>

- **No fees** - x402 as a portocol has 0 fees for either the customer or the merchant.
- **Instant settlement** - Accept payments at the speed of the blockchain. Money in your wallet in 2 seconds, not T+2.
- **Blockchain Agnostic** - x402 is not tied to any specific blockchain or token, its a neutral standard open to integration by all.
- **Frictionless** - As little as 1 line of middleware code or configuration in your existing web server stack and you can start accepting payments. Customers and agents aren't required to create an account or provide any personal information.
- **Security & trust via an open standard** - Anyone can implement or extend x402. It's not tied to any centralized provider, and encourages broad community participation.
- **Web native** - Activates the dormant 402 HTTP status code and works with any HTTP stack. It works simply via headers and status codes on your existing HTTP server.
</blockquote>

<p class="links bottom-4!">🔗<a href="https://www.x402.org" target="_blank">x402.org</a></p>
</div>
<iframe
  src="https://www.x402.org/x402.pdf#toolbar=0&navpanes=0&zoom=page-width"
  class="w-7/16 h-full absolute right-0 top-0"
  loading="eager"
  />
<p class="links">🔗<a href="https://www.x402.org/x402.pdf" target="_blank">x402.org/x402.pdf</a></p>

---

|| __Traditional Payment__ | __Crypto__ | __x402__ |
| ---- | ---- | ---- | ---- |
| Buyer | Credit cards, Bank debits,<br> Bank tranfers, Vouchers,<br> Payment providers<br>(apple pay, google pay...) | Wallet address<br>-> Expandable via web3 | Wallet address<br>-> Expandable via web2/web3 |
| Buyer KYC | <span class="marker">Payment vendor</span> | - | - |
| Seller | Bank account | Wallet address<br>-> Expandable via web3 | Wallet address<br>-> Expandable via web2/web3 |
| Seller KYC | <span class="marker">Payment vendor</span> | - | - |
| Fee | 3.6% | tx gas fee | tx gas fee (0: USDC on BASE) |
| Payment verification | <span class="marker">Payment vendor</span> | Blockchain | <span class="marker pink">Facilitator(Blockchain)</span> |

---

# x402 protocol

### Facilitator Responsibilities

<div class="text-xl mt-4">

- __Verify payments__: Confirm that the client's payment payload meets the server's declared payment requirements.
- __Settle payments__: Submit validated payments to the blockchain and monitor for confirmation.
- __Provide responses__: Return verification and settlement results to the server, allowing the server to decide whether to fulfill the client's request.
</div>

---

# x402 protocol

- Url based payment handling
- ❌ Subscription -> Need seller server impl
- ❌ Time based content access -> Need seller server impl

```js
// Configure the payment middleware
app.use(paymentMiddleware(
  "0xYourAddress", // your receiving wallet address
  {  // Route configurations for protected endpoints
    "/protected-route": {
      price: "$0.10",
      network: "base-sepolia",
      config: {
        description: "Access to premium content",
      }
    }
  },
  {
    url: "https://x402.org/facilitator", // Facilitator URL for Base Sepolia testnet.
  }
));

```

---

# x402 implementation

<div class="grid grid-cols-3 gap-4">
  <div>
    For example, since they are just HTML headers, they can only return minimal fallback HTML.<br>
    Customization is necessary to sell products or provide a rich experience.
    <code class="mt-4 text-xs!">https://x402.org/ptrotected</code>
    <img src="/assets/14/x402-protected.png" class="mt-4" />
  </div>
  <div>
    <code class="text-xs!">https://*/p/73WakrfVbNJBaAmhQtEeDv</code>
    <img src="/assets/14/x402-demo0.png" class="mt-2 w-4/5" />
  </div>
  <div>
    <code class="text-xs!">https://*/p/73WakrfVbNJBaAmhQtEeDv/protected</code>
    <img src="/assets/14/x402-demo1.png" class="mt-2 w-4/5" />
    <p class="text-sm">Separate protected content url and query API if x402 payment verified</p>
  </div>
</div>

---

# x402 use cases

### Some services based x402 protocol

- https://h402.xyz/ -> multichain
- https://catenalabs.com/ -> AI payment

<br>

### Some ideas / features

- Replace existing payment service with extra-low fee
- Escrow servise to verify payment /w x402 `e.g) mercari, ebay`
- Access control with any ERC-20
- Private IPFS network for file shareing gateway url handling /w x402
- Native support for Browsers/API Client -> <span class="marker">No need for SDK</span>

---

# 💬 Final thoughts

<div class="text-3xl pt-2">

- Blockchain is fundamentally trustless, but for the sake of UX, some degree of trust and reliance on third parties has been inevitable
- `x402` and `porto` aim to <span class="marker blue">minimize trust points while pushing UX and use cases</span> to the next phase
- Aligned with <span class="marker green">Ethereum’s Public Goods</span>
- Build on Ethereum 🩷
</div>
