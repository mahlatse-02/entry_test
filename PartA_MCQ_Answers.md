# Part A: MCQ Answers

**Status:** [In Progress / Submitted]

**Marks:** 24 for the letters (3 each) + 16 for your reasoning (2 each) = **40 of 100**

---

## Instructions

**COMPLETE ALL QUESTIONS FOR BOTH PART 1 AND PART 2 BELOW**

Every question here is covered by **Cyfrin Updraft - Blockchain Basics**. If you
worked through that course, you have already been taught all of this.

**How to answer:** replace the placeholder on the `**Your Answer:**` line with a
single letter, like this:

```
**Your Answer:** B
```

The auto-marker reads that line. Write only the letter - no brackets, no
explanation on that line.

> [!IMPORTANT]
> **Your answers lock on the first push where all eight are filled in.** Decide
> on all eight, then push them together - changing them afterwards will not
> change your score.

Your reasoning goes in the box underneath and is marked separately, 2 marks
each. **A blank reasoning box scores zero**, so write two or three sentences
even when the answer is obvious.

---

## PART 1: Blockchain Fundamentals

---

### Question 1: Why a Blockchain At All? (3 marks + 2 for reasoning)

A community savings group asks: *"Why can't we just use a normal website with a
database?"*

**Which response shows real understanding of what a blockchain gives you?**

- **A)** "Blockchain is the future and everyone should be using it."
- **B)** "Because no single party controls the record. Every member can verify
  the contribution and payout history themselves, and no administrator - not
  even us - can quietly edit it after the fact. A database is faster and
  cheaper, so the trade is worth it only when the members do not fully trust
  whoever runs the server."
- **C)** "Because blockchains use cryptography, which makes them unhackable,
  unlike normal databases."
- **D)** "Because a database can only handle a few thousand users, and
  blockchains scale infinitely."

**Your Answer:** B

**Your Reasoning:**
With the management of funds in a group, the most important measure is to ensure that there are no members in the group that tamper with any of the transactions that are made. The blockchain ensures this by having a decentralised network where all members can review and approve or decline transactions before processing. This ensures safety of the funds and less tampering, whereas, a database requires an individual to manage and keep running.

---

### Question 2: Gas Costs (3 marks + 2 for reasoning)

You send a simple ETH transfer on Ethereum.

- **Gas used:** 21,000
- **Gas price:** 20 gwei
- **1 ETH = $3,000**

**What does the transaction cost?**

- **A)** 0.042 ETH (about $126)
- **B)** 0.000021 ETH (about $0.06)
- **C)** 0.00042 ETH (about $1.26)
- **D)** 0.0042 ETH (about $12.60)

**Your Answer:** C

**Your Calculation:**
Total gas cost in gwei = 21 000 x 20 gwei = 420 000 gwei
Total gas cost in ETH = 420 000 x 10^-9 = 0.00042 ETH 
Total gas cost in $ = 0.00042 x 3 000 = $1.26

- Total gas cost in gwei = [show your working]
- Converted to ETH (remember: 1 ETH = 1,000,000,000 gwei) = [show your working]
- Converted to USD = [show your working]

[Then, in one or two sentences: why does a smart contract function that writes
to storage cost far more than this simple transfer?]


---

### Question 3: The Oracle Problem (3 marks + 2 for reasoning)

Your smart contract needs to know the current ETH/USD price.

**Why can't the contract simply call a price API itself?**

- **A)** Because API calls are too expensive in gas, though they are technically
  possible.
- **B)** Because every node on the network must execute the same transaction and
  reach the same result. If each node called an API it might get a slightly
  different answer, and the nodes could never agree on the outcome. An oracle
  solves this by putting the data on-chain first, so every node reads the same
  stored value.
- **C)** Because Solidity has no networking library yet, but this is being added
  in a future upgrade.
- **D)** Because API providers block blockchain nodes for security reasons.

**Your Answer:** B

**Your Reasoning:**
A decentralised oracle network ensures that whatever code or logic is in the blockchain cannot be changed after deployment  to ensure uniform data that is distributed to each node that is part of the network. This is done by giving the specific block a hash that is used for identification. A contract can also not be changed unless it is upgradable, which mean for an update to occur, a new block would have to have the modified contract which will have its own hash.
---

### Question 4: Consensus and Attacks (3 marks + 2 for reasoning)

**Which statement about Proof of Stake is correct?**

- **A)** Validators compete to solve a cryptographic puzzle, and the fastest one
  wins the right to propose a block.
- **B)** Proof of Stake removes the possibility of a majority attack entirely,
  because there is no mining.
- **C)** Any node can propose blocks for free, which is what makes Proof of Stake
  cheaper than Proof of Work.
- **D)** Validators lock up capital as stake to earn the right to propose and
  attest blocks. Misbehaviour can be slashed, so attacking the chain costs the
  attacker their own stake. The cost of that stake is also what makes Sybil
  attacks - one actor spinning up thousands of fake nodes - uneconomic.

**Your Answer:** D

**Your Reasoning:**
An attacker can create multiple nodes so that they can have majority rule over the blockchain. This results in the threatened security of all the other legitimate transactions that have been made in the network. Proof of work solves the problem where for each transaction made, therre has to be an amount that is paid to the processors of the transaction for approving the transaction.

---

### Question 5: Layer 2s and Rollups (3 marks + 2 for reasoning)

**How does a rollup make transactions cheaper than Ethereum mainnet?**

- **A)** It executes transactions off-chain, then posts the compressed results
  (with either a validity proof or a fraud-proof window) back to Ethereum. The
  cost of that single L1 posting is shared across all the transactions in the
  batch, so each user pays a fraction of it while still inheriting Ethereum's
  security for final settlement.
- **B)** It uses a faster consensus algorithm than Ethereum, so blocks are
  produced more cheaply.
- **C)** It stores transactions in a private database and never touches
  Ethereum, which is why it costs almost nothing.
- **D)** It reduces gas costs by lowering the base fee on Ethereum itself
  whenever the rollup is active.

**Your Answer:** A

**Your Reasoning:**
The sequencer allows one to choose a fee that is proportional to the processing time where the higher the price, the faster the transaction procesing because nodes will choose to gain a higher currency value. When this is done on a rollup, the shared transaction cost decreases 
---

### Question 6: Wallets, Keys and Signatures (3 marks + 2 for reasoning)

A new user asks why they need a seed phrase, and why you cannot reset it for
them.

**Which explanation is correct?**

- **A)** The seed phrase is a password stored on the blockchain, so only the
  network can reset it.
- **B)** The seed phrase encrypts your funds where they sit on the chain. Losing
  it means your funds stay encrypted forever.
- **C)** Your seed phrase derives your private key, and your private key produces
  signatures that only your address can produce. That signature is how a
  contract knows a transaction is really from you, without anyone needing to
  approve it. Nobody else holds a copy, so nobody - including us - can restore
  it or reverse a transaction you signed.
- **D)** The seed phrase is just a backup of your public address, which is why it
  is safe to share with support staff if you get stuck.

**Your Answer:** C

**Your Reasoning:**
The signature proves that the node is part of the network. The trade off of a user being in possession of their own keys is compromising security measures where a user can have their private keys stotrd in a place that is visible to other users or the public that can attack the network. Account abstraction solves this by writing the keys in hash that cannot be readable 
---

## PART 2: Applying It To Your Contracts

These two questions connect directly to the code you write in Part B. Answer
them before you start coding - they will save you time.

---

### Question 7: Randomness On-Chain (3 marks + 2 for reasoning)

Your raffle needs to pick a winner. A developer suggests:

```solidity
uint256 index = uint256(
    keccak256(abi.encodePacked(block.timestamp, block.prevrandao))
) % players.length;
```

**What is wrong with this?**

- **A)** Nothing. Hashing block data produces a value nobody can predict, which
  is exactly what randomness means.
- **B)** Every input here is public on-chain data, and the block proposer has
  some influence over it. Anyone can compute the same result inside the same
  block and act only when it favours them, and a proposer can drop or reorder a
  block to change the outcome. Real randomness has to come from outside the
  chain, verifiably - a service like Chainlink VRF, or a commit-reveal scheme.
- **C)** The problem is only the modulo, which introduces a small bias. Swapping
  to a different hash function fixes it.
- **D)** It is insecure on Ethereum but safe on a Layer 2, because the sequencer
  orders transactions privately.

**Your Answer:** B

**Your Reasoning:**
The labelled owner is the only one who can manipulate the draw by changing the number of players that are stored in the list. This would be biased in a sense that the owner can repeatedly draw from a player that is desired by them.

---

### Question 8: Paying Out Safely (3 marks + 2 for reasoning)

This function pays a freelancer:

```solidity
function approveAndPay(uint256 bountyId, address freelancer) external {
    Bounty storage b = bounties[bountyId];
    require(msg.sender == b.employer, "Not the employer");

    (bool ok, ) = freelancer.call{value: b.amount}("");
    require(ok, "Transfer failed");

    b.status = Status.Completed;
}
```

**What is the bug?**

- **A)** Nothing is wrong - the return value of `call` is checked, which is what
  matters.
- **B)** `call` is unsafe and should be replaced with `transfer`, which is the
  standard way to send ETH securely.
- **C)** The status is updated *after* the ETH is sent. If the freelancer is a
  contract, its receive function runs during that call and can call
  `approveAndPay` again while the status is still un-updated, draining the
  contract. The fix is checks-effects-interactions: set the status to Completed
  before sending.
- **D)** The `require` on `msg.sender` should use `tx.origin` instead, so that
  contracts cannot call the function at all.

**Your Answer:** C

**Your Reasoning:**
An attacker would make multiple payments to the same address multiple times because there is no check to verify if the freelancer has been paid before making a payment.

---

## SUBMISSION CHECKLIST

- [X] Every `**Your Answer:**` line contains a single letter and nothing else
- [X] You gave reasoning for all 8 questions
- [X] For Question 2 you showed your working
- [ ] You committed and pushed to your fork

---

**Challenges faced:** [What was difficult? Which concepts are you least
confident about? Answering this honestly does not cost you marks.]
The logic behind identifying where an attacker would identify a vulnerability in the code because I am not overly familliar with the flow of logic when it comes to smart contracts and security measures 
