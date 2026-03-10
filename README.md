# Numbers War: Grand Drop
A trustless competitive gaming economy built on Avalanche.  Transparent match results, on-chain player identity,  and a skill-based reward system.

---
Welcome to Numbers War: Grand Drop a competitive Web3 
multiplayer game and the newest member of the Numbers War family.

> [!IMPORTANT]
> You can play the game with friends Here [Numbers War: Grand Drop](https://khalilakm.itch.io/numbers-war-grand-drop-prototype), if the page is protected with a password just type: GrandDrop2026#

---
## Gameplay Overview
*Numbers War: Grand Drop isn't just a game—it’s a solution to the "Broken Economy" problem in Web3. While others focus on just playing, we focus on problem-solving through skill-based mechanics.*

## 🎮 The Core Loop
Players enter a chaotic multiplayer arena using Tickets. Once the round starts, "Grands" and various weapons (including jetpacks) are dropped from a plane. Your goal: collect as many Grands as possible while surviving the crossfire.

![](https://img.itch.zone/aW1nLzI2MDQ4MjMwLmpwZw==/original/AJULu9.jpg)

💀 The Death & Drop Mechanic
Success is entirely skill-dependent. The more you die, the more "fragile" your loot becomes. Your drop rate is calculated based on your death count:

| Death Count  | % of Collected Grands Dropped |
| ------------- | ------------- |
| 0 Deaths  | 0% (Safe)  |
| 1st Death  | 10%  |
| 5th Death  | 50%  |
| 10+ Deaths  | 100% (Everything drops)  |

Strategy Tip: As your death count rises, your tactics must change. High-scoring players become the biggest targets, forcing a shift from aggressive collecting to defensive survival.

## 🎟️ The Ticket Economy
There are two ways to enter a match, each affecting how you interact with the marketplace:

Normal Tickets: **Cost: 100 Grands**.

Function: Purchased Grands are sent to the GrandDrop contract to fund the rewards for that session.

Restriction: These are bound to your account and cannot be sold.

Rewarded (Discounted) Tickets:

How to earn: **Completed in-game missions**.

Value: Discounts can reach **100%**, allowing skilled players to play for free.

Utility: Unlike normal tickets, these can be listed for sale on the marketplace for Grands.

|<img src="https://img.itch.zone/aW1nLzI2MDQ4MzExLnBuZw==/200x150cm/ELAqVB.png" width="100">
<img src="https://img.itch.zone/aW1nLzI2MDQ4MzEyLnBuZw==/200x150cm/XCaRt0.png" width="100">
<img src="https://img.itch.zone/aW1nLzI2MDQ4MzE2LnBuZw==/200x150cm/NWlmzL.png" width="100">
<img src="https://img.itch.zone/aW1nLzI2MDQ4MzE0LnBuZw==/200x150cm/zcTMBG.png" width="100">
<img src="https://img.itch.zone/aW1nLzI2MDQ4MzE1LnBuZw==/200x150cm/czz3oH.png" width="100">|

## 💰 Earning & Cashing Out
Players profit by being skilled enough to keep their collected Grands or by farming mission-based tickets to sell to other players.

* Grands can be sold back to the GrandToken Contract.

* Specific restrictions apply to these withdrawals to maintain economic balance (detailed in the Smart Contracts section).


## 🔺 On-Chain
The speed and low gas fees made this entire experience possible. Session creation, claims, ticket trades, profile updates  all happening on-chain without making players wait or pay a fortune. Building a real-time competitive game on blockchain only works when the infrastructure doesn't get in the way. Avalanche doesn't. 🔥⚡

The entire economy of Grand Drop runs on three smart contracts **GrandToken**, **GrandTicket**, and **GrandDrop**. Each one has a specific responsibility, and together they form a complete, trustless system.
Let's walk through each contract and break down the most important functions what they do, why they exist, and how they protect the player.

# GrandToken
Address: [0x7F2F22647157Be49464e4082C54D5067fcA0d009](https://testnet.snowtrace.io/address/0x7F2F22647157Be49464e4082C54D5067fcA0d009/contract/43113/code) | Avalanche Fuji Testnet

**GrandToken** is the **ERC20** contract that powers everything. It's the **blood** of the entire system.

**One million GRAND** minted at deploy locked inside the contract itself. Not in a dev wallet, not under anyone's control. The contract holds the supply and the **AVAX** reserve. 

Players buy **GRAND** from it, sell **GRAND** back to it, and every in game transaction flows through it.

Two rules that never change only the game contract can move **GRAND** between players, and nobody can mint more. Ever.

Simple, transparent, and completely on-chain.

- Three functions. That's all it takes to run a fully trustless token economy.
 
**BuyGrands:** You send **AVAX**, you get **GRAND**
- A balance cap. No single player can hold more than **5,000 GRAND** at once. This keeps the economy healthy and prevents any one player from dominating the supply.
- The contract checks it actually has enough GRAND in reserve before sending. No overselling, no empty promises.
 
**GameTransfer**: This is the most important security function in the entire contract.
  - In a normal **ERC20** token, anyone can call transfer and move tokens around freely. That's a problem in a competitive game economy you don't want players moving **GRAND** around outside of the game rules.
GameTransfer solves that. It's the only way **GRAND** moves between addresses  and it can only be called by one address. The game contract. Nobody else.
Player to contract. Contract to player. Contract to contract. Every single **GRAND** movement in the entire economy goes through this one function, authorized by one address.
If someone tries to call it directly rejected. If a random contract tries to call it rejected. Only **GrandDrop**, **GrandTicket** and **GrandDrop** are authorized. That's it.
One function. One rule. Total control over every transaction in the economy."

**GameTransferAVAX:** If GameTransfer controls how GRAND moves — GameTransferAVAX controls how real money moves.
- When a player sells their **GRAND**, they get **AVAX** back. That **AVAX** has to come from somewhere it comes from the contract's reserve. The same reserve that was built up from every player that ever bought **GRAND**.
**GameTransferAVAX** handles that payout. And just like **GameTransfer** only the game contract can call it. Nobody else can touch the **AVAX** reserve.
But there's one more protection before sending anything, the contract checks it actually has enough **AVAX** to cover the payout. No bounced transactions, no failed withdrawals.
The split is transparent and fixed a small percentage goes to **Admin** to cover session gas fees, a small percentage goes to Dev to cover server costs, and the rest goes straight to the player.
Every number is on-chain. Every fee is public. Nothing is hidden."

# GrandTicket
Address: [0x48C880BC30859fd36B02628e70b4165B92c867bE](https://testnet.snowtrace.io/address/0x48C880BC30859fd36B02628e70b4165B92c867bE/contract/43113/code) | Avalanche Fuji Testnet

**GrandTicket** The Gateway to Competition GrandTicket is the ERC1155 contract that manages every ticket in the game

Five tickets exist in the Grand Drop universe:
- **Normal:** the standard entry ticket. Bought with GRAND.
- **Bronze:** 10% discounted entry. Earned through performance.
- **Silver:** 50% discounted entry. Earned through skill.
- **Gold:** 75% discounted entry.
- **Platinum:** 100% free entry. Earned through mastery.

The higher the ticket the harder it is to earn. And the more valuable it becomes on the marketplace.

  


