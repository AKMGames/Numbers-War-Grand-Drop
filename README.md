# Numbers War: Grand Drop
A trustless competitive gaming economy built on Avalanche.  Transparent match results, on-chain player identity,  and a skill-based reward system.

---
Welcome to Numbers War: Grand Drop a competitive Web3 
multiplayer game and the newest member of the Numbers War family.

> [!IMPORTANT]
> You can play the game with friends Here [Numbers War: Grand Drop](https://khalilakm.itch.io/numbers-war-grand-drop-prototype), if the page is protected with a password just type: GrandDrop2026#

> [!CAUTION]
> The game uses [Edgegap](https://edgegap.com/) free plan for hosting the dedicated server, Free plane gives a Matchmaker that lasts 1 hour and then shuts down, i need to reactivate it manually to get a new 1 hour, i'm afraid you test the game while the mathchmaker is not live, i'll try my best to update it evey hour, i'm really sorry, i'cant aford to buy a plan, please if you face any network problem during joining the session please contact me so i can activate the mathchmaker or any Avalanche support reach me so i can reactivate the mathchmaker, i'm really sorry.
> telegram & Discord: khalilakm  | email: hammoudakhalil5585@gmail.com

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

## Greate Account:

<img src="https://img.itch.zone/aW1nLzI2MDY4NDYzLmdpZg==/original/TxERn8.gif">

## Buy Grands:

<img src="https://img.itch.zone/aW1nLzI2MDY4NTc4LmdpZg==/original/J%2F6K1k.gif">

## Buy Tickets:

<img src="https://img.itch.zone/aW1nLzI2MDY4NTkwLmdpZg==/original/MBQ5vP.gif">

## Join Game:

<img src="https://img.itch.zone/aW1nLzI2MDY4NjgwLmdpZg==/original/I9jCgx.gif">

## Collect Grands & Weapons:

<img src="https://img.itch.zone/aW1nLzI2MDY4NjgzLmdpZg==/original/erbL0z.gif">

## Claim:

<img src="https://img.itch.zone/aW1nLzI2MDY4NzE0LmdpZg==/original/dRuZDo.gif">

## List Tickets:

<img src="https://img.itch.zone/aW1nLzI2MDY4NzI3LmdpZg==/original/%2BUAD7%2F.gif">

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

 - Important functions:

**BuyNormalTicket:** Simple and transparent.
- Player spends 100 GRAND goes straight into the match pool inside **GrandDrop**, No middleman. No platform fee. You know exactly where every GRAND goes the moment you buy.

**GameMint:** This is how reward tickets are born.
- Only Contracts can call this function nobody else. When a player earns a reward at the end of a match, **GrandDrop** calls GameMint and the ticket appears in their wallet. No buying. No shortcuts. You earn it or you don't

**ListTicket:** This is where the player economy comes alive.
- Earned a Gold ticket but don't need the discount right now? **List it**. Set your price in **GRAND**, and the ticket goes into escrow inside the contract safe, locked, and visible to every player on the **marketplace**.

**BuyTicket:** The other side of the marketplace.
- See a Gold ticket listed for a good price? Buy it. **GRAND** goes straight to the seller, ticket comes straight to you. No waiting, no approval, no middleman.
  
# GrandDrop (my favourite)
Address: [0xcC749aA09217E82269C2E192aA41a3d359677413](https://testnet.snowtrace.io/address/0xcC749aA09217E82269C2E192aA41a3d359677413/contract/43113/code) | Avalanche Fuji Testnet

This is where everything comes together. **GrandToken** handles the currency. **GrandTicket** handles the entry. **GrandDrop** handles everything else, player profiles, match sessions, result verification, prize distribution, and the sell economy.
Every player interaction that matters happens here. Every GRAND won in a match flows through here. Every match result is verified here.
**Three roles keep the system in balance:**
- **The Owner:** deploys the contract, sets the admin, nothing else.
- **The Admin:** the server wallet. Creates sessions, signs match results, cannot be a player, cannot hold **GRAND**
- The Player everyone else. Competes, earns, trades, cashes out.
  No role can cross into another. The contract enforces every boundary. This is the contract that makes Grand Drop trustless.

- Top functions:

**CreateProfile:** Before anything else you need an identity.
- CreateProfile is the first transaction every player makes. Choose a username, confirm it on-chain, and from that moment you exist in the Grand Drop universe permanently.
- But there are rules. **Owner** cannot create a profile. **Admin** cannot create a profile. This keeps the people running the system completely separate from the people playing it. No insider advantage. No hidden accounts.

**CreateSession:** This is where a match becomes real.
- When the server finds a full lobby, it calls CreateSession on-chain. Player addresses, their ticket types, the session ID all recorded on Avalanche in one transaction.
- The moment this function runs: Every ticket is burned — no going back.Every player's pool contribution is calculated and locked. The session is live on-chain.
- Normal ticket holders already pre-paid their pool value at BuyNormalTicket nothing extra pulled from them.
- Reward ticket holders pay their discounted amount directly Bronze pays 90, Silver pays 50, Gold pays 25, Platinum pays nothing
- The pool is locked. The match starts. The contract is now holding every GRAND that will drop from that plane.
- Only Admin can call this function. And Admin cannot play. The separation is absolute.

**Claim:** This is the most important function in the entire system.
- Match ends. Server calculates everything how many Grands you collected, how many kills, how many deaths. Then it signs that result cryptographically and sends it to the player.
- Player submits that signature to the contract. The contract verifies it  was this actually signed by Admin? Is the nonce correct? Does this player have an active session? Is the profile real?
- Every check passes **GRAND** is transferred instantly. Profile stats updated permanently. Reward ticket minted if earned.
- Every check fails transaction rejected. No result can be faked. No amount can be inflated. No kill count can be manipulated.
- The nonce is critical here it's a unique number that increments after every claim. The same signature can never be used twice. Ever.

**AbandonSession:** Not every player finishes what they started.
- If a player disconnects, rage quits, or simply leaves mid match they call **AbandonSession**. Or the server detects it and handles it.
- The punishment is immediate the player is banned for a set duration. No rejoining, no claiming, no new sessions until the ban expires. The longer the ban duration, the more it hurts to quit.
- Their share of the pool doesn't disappear though. It stays locked in the session. When the match ends and the session finalizes any unclaimed **GRAND** goes to Dev to cover server costs. Nothing is wasted.
- Quitting has consequences. Staying and fighting has rewards. That's how you keep players honest.

**SellGrands:** This is where skill becomes real money.
- Accumulated enough **GRAND** from winning matches? Sell it back to the contract for **AVAX**. But not just anyone can sell the system is designed to protect the economy from exploitation.
- Three gates to pass:
   - **First:** match history. You need at least **10 matches** played before you can sell anything. The more matches you've played, the more you can sell per transaction. Casual players have limits. Veterans have more freedom.
   - **Second:** minimum balance. You can never sell everything. A minimum amount must stay in your wallet you're a player, not a bank.
   - **Third** cooldown. **Three days** between every sell. No farming, no dumping, no exploiting the reserve.
- Pass all three **GRAND** goes back to the contract, **AVAX** comes to you. Small fees split to Admin and Dev to cover running costs. The rest is yours. Earned through skill. Protected by rules. Paid in **AVAX**."

**SweepSessions:** The cleanup crew.
- Sometimes sessions don't finalize cleanly all players abandon, nobody claims, the match just dies. These ghost sessions would sit on-chain forever, locking **GRAND** inside them with no way out. SweepSessions solves that.
- **Admin** calls this function periodically. It scans every active session and checks one thing has it been more than **24 hours** since it was created? If yes it's dead. Leftover **GRAND** goes to **GrandToken**, One function. Keeps everything clean. Keeps the economy moving.


## One last thing I want to be transparent about:
*Before this jam, I had zero knowledge of Solidity. Zero experience writing smart contracts. It may not be perfect. There may be edge cases I didn't catch, optimizations I missed, or patterns a seasoned Solidity developer would do differently. I know that. And I own it.*
*And none of this would have been possible without **Avalanche**. The speed, the low gas fees, the developer ecosystem everything just worked. Avalanche didn't get in the way of the vision. It enabled it. Thank you. 🙏*




  


