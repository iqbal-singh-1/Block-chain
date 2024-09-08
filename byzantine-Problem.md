# What is Byzantine General’s Problem?
In 1982, The Byzantine General’s Problem was invented by Leslie Lamport, Robert Shostak, and Marshall Pease. Byzantine Generals Problem is an impossibility result which means that the solution to this problem has not been found yet as well as helps us to understand the importance of blockchain. It is basically a game theory problem that provides a description of the extent to which decentralized parties experience difficulties in reaching consensus without any trusted central parties.

1. The Byzantine army is divided into many battalions in this classic problem called the Byzantine General’s problem, with each division led by a general. 
2. The generals connect via messenger in order to agree to a joint plan of action in which all battalions coordinate and attack from all sides in order to achieve success. 
3. It is probable that traitors will try to sabotage their plan by intercepting or changing the messages. 
4. As a result, the purpose of this challenge is for all of the faithful commanders to reach an agreement without the imposters tampering with their plans.
# Money and Byzantine General’s Problem
- Money is one of the most important resource one needs to survive in today's world. However, it is still controlled by centralised system. They can easily control the inflation and decide the value of money like this note is worth this much and this is worth that much. 
- They do not provide transparency about their working techinques which is a big loop hole.
- They can easily by corrupted or controlled by centralized authorities like goverments meaning no truthfulness.
# Solution to Byzantine General’s Problem
- To solve the problem, we use block-chain.
- Let us assume that generals in byzantine represent nodes in block-chain. Now, we provide the solution by using the majority kind of concept. If 51% or more nodes agree on a decision, suppose 3 of 4 generals want to attack the kingdom, then the decision will be made and any other decision will be discarded. There are few protocols associated with block-chain that ensures the integrity of data.

1. <b>Proof Of Work</b>(Consensus - A): The network would have to be provable, counterfeit-resistant, and trust-free in order to solve the Byzantine General’s Problem. Bitcoin overcame the Byzantine General’s Problem by employing a Proof-of-Work technique to create a clear, objective regulation for the blockchain. Proof of work (PoW) is a method of adding fresh blocks of transactions to the blockchain of a cryptocurrency. In this scenario, the task consists of creating a hash (a long string of characters) that matches the desired hash for the current block.
<br>
    1. This protocol makes sure that the new blocks that are generated cannot be tempered once made and accepted by the society. The work of miner is checked and if it is valid, they are provided with a huge reward. Failing to prove their work might mean penalities applied to the miner costing him much more than the reward he was going to get.
    2. It becomes difficult to dettach a block once it has been attached in the block-chain. So, each node in the block-chain verifies if the block is valid or not before attaching it to the chain. So, the work is validated by all the nodes in the block-chain.
    3. As we know each node verifies the blocks itself, there is no dependency of one node on the other of validating data in the block, making them independent on their on own.
Voting is done and the party with more than 51% of nodes wins.

2. <b>Longest Competing chain</b>(Consensus - B): This protocol is used when more than one chains co-exist in the blockchian. For eg:- If one miner has mined a block and at the same time another miner has also mined the other block, there would be difference in blocks of both the chains and the nodes nearest to the respective miners will have chains of blocks made according to that. Now, 2 different chains co-exists at the same time. So, to avoid such a scenario, we say that the chain which gets bigger earlier than the other in the network will be considered and the blocks discovered by other miner will be discarded.

# Byzantine Fault Tolerance
The Byzantine Fault Tolerance was developed as inspiration in order to address the Byzantine General’s Problem. The Byzantine General’s Problem, a logical thought experiment where multiple generals must attack a city, is where the idea for BFT originated.

- Byzantine Fault Tolerance is one of the core characteristics of developing trustworthy blockchain rules or features is tolerance.
- When two-thirds of the network can agree or reach a consensus and the system still continues to operate properly, it is said to have BFT.
- Blockchain networks’ most popular consensus protocols, such as proof-of-work, proof-of-stake, and proof-of-authority, all have some BFT characteristics.
- In order to create a decentralized network, the BFT is essential.
### Citing source :- Geeks For Geeks
 