---
title: 'Adverserial Signaling Games: Quantum Approach'
date: 2025-05-06
permalink: /posts/2025/05/Adveserial-Games-Quantum/
tags:
  - Adverserial Signaling Games
  - Quantum Games
excerpt: We describe an adversarial Signaling game as a two player game, where each player has the capacity to manipulate a shared environment. Additionally each player can observe the others' actions along with the effect of those actions on the shared environment. Hidden intention's, however, may remain obfuscated. Within this game structure there are a few features to take note of which we describe bellow along with an examples from finance, military strategy, political strategy and cyber secruity. 
---

We describe an adversarial Signaling game as a two player game, where each player has the capacity to manipulate a shared environment. Additionally each player can observe the others' actions along with the effect of those actions on the shared environment. Hidden intention's, however, may remain obfuscated. Within this game structure there are a few features to take note of which we describe bellow along with an examples from finance, military strategy, political strategy and cyber secruity. 

<!--more-->

- **Misleading Signals:** The purpose of each players' actions is two fold. First they seek to manipulate their environment in order to create favorable conditions that allow them to maximize some objective. Second each player may take an action to manipulate not the environment but the other player's actions. For example, player A may seek to establish a intentionally deceptive repeated pattern of actions in order to lure player B into a particular action strategy, before suddenly breaking that pattern to reap a reward. This is not an unusually strategy nor is particularly novel. Take for example the mythologized Trojan war described in Homer's *Iliad* where the Achaeans intentionally established an observable pattern of peace by retreating their forces and offering the Trojans a "gift". The Trojans were lulled into a belief that the threat had passed leading them to lower their defenses and giving the Achaeans a window to launch a final strike. In other words one player took repeated actions that created a false expectation and manipulated the actions of their competitors before breaking that pattern to reap a reward. 

- **Two-Stage Learning:** Note that within an adversarial signaling game there is latent information asymmetry. Namely that each player has a set of hidden intentions and observable actions. If a player were to only analyze the observable actions of their competitor then they will be manipulated and eventually beat. To avoid this outcome and fate similar to the Trojans, each player must learn to do two things. They must first, learn how to detect patterns within the observable actions of their competitor. Second they must learn to evaluate those patterns and decide whether their opponent is intentionally deceiving them or whether the pattern they are observing can be exploited. For example imagine two high frequency equity traders. Trader A seeks to manipulate their competitors by placing a sequence of intermittent large buy orders which increase the price of the equity. Trader B observes the pattern and may decide to buy the equity before Trader A's anticipated buy order in order to profit from the price jump induced by Trader A's periodic buy orders. However Trader A sells the equity while the price is high leaving Trader B with a loss. On the other hand Trader B may decide to stay out of the market by anticipating Trader A's attempts at market manipulation. Trader B may also anticipate Trader A's intention to offload the asset and decide to short the equity beforehand in order to take advantage of Trader A's hidden intention. In other words Trader B must not only detect the patterns but must also infer the hidden intention behind the pattern in order to make a "winning" decision.

- **Iterative Structure and Early Stage Interactions:** Within the adversarial signaling game each player must observe repeated actions in order to make reasonable and educated inferences about the other player. This means that the game cannot be captured by a one-shot static model such as that proposed within optimal auction theory or a prisoner's dilemma type game. However, the player may be able to bring a set of pre-existing beliefs into an interaction with a player in order to avoid the "cold-start" problem. In this scenario it may be advantageous to employ meta-strategies like randomized actions to avoid the risk of one's strategy being immediately anticipated by an opponent with an accurate set of pre-existing beliefs and to functionally nullify any pre-existing beliefs or strategies an opponent may have within the first couple of interactions of the game. By denying the opponent predictable action structures in the early phase of the game, a player can force an opponent into uncertainty, delaying exploitation or even misleading them into classifying the system incorrectly. All of which force a "cold start" and wipe out any advantage an opponent may have had when they entered the game. Take for example a hacker attempting to infiltrate a server through a given port they believe to be open. Often times the first response of the server is to randomly deny or silently drop a server request from an unknown or suspicious IP address, which induces ambiguity. In other words the hacker's pre-existing belief that the port is open is now called into question which forces a cold start and wipes out the hacker's informational advantage. 


There are various mathematical tools one could use to formalize this type of two player game, however for the sake of this proposal we choose one non-classical and one classical formalization to explore. First we explore repeated quantum games and their ability to incorporate uncertainty and non-classical signal-detection strategies.  Second we examine the potential for stochastic/differential games to capture continuous time learning, environment evolution, and optimal deception. 



Quantum Games
======

The first potential approach is the use of repeated quantum games to model the two-player adversarial game. This approach was first popularized with the introduction of the quantum prisoners dilemma, which serves as a pedagogical example for how this quantum game theory applies to the setting described above. For that purpose we spend some time discussing its implementation and how it can generalize to different scenerios we might wish to model. 


Repeated Quantum Prisoners Dilemma (QPD)
------

In the classical version of the quantum prisoners dilemma there are two players who can choose to either cooperate (C) or defect (D). The joint action of the two players results in a certain payoff for each player.Bellow we illustrate a potential payoff structure. 


|                | Player B: C | Player B: D |
|----------------|-------------|-------------|
| **Player A: C** | (3, 3)     | (0, 5)     |
| **Player A: D** | (5, 0)     | (1, 1)     |

This game structure creates a tension between deceiving your opponent or believing your opponent will do whats best of both players. Classicaly the dominant strategy is to always defect which results in a Nash equilibrium of (D,D). Note that the Nash equilibrium does not correspond with the Pareto optimal solution which is to always cooperate in order to maximize the outcome for both players. Often times a players strategy may not be as black and white as cooperating or defecting. Instead of the player may opt to cooperate for a time while hiding their true intentions of lowering their opponents defense and eventually defecting. Additionaly in the classical case the two players do not interact which we is unrealistic for modeling real world game dyanamics. In the quantum prisoners dilemma (QPD) this problem is addressed by allowing players to both defect and cooperate simultaneous (i.e the QPD allows for mixed strategies and implicit communication). The game starts with an two-qubit entangled state $$\ket{\psi_0}$$, where $$J \in \mathcal{H}$$ is some unitary operator that produces an entangled state where the two players are in a superposition of both cooperating and defecting. Note that $$\gamma$$ affects the degree to which the two players are entangled, which we will discuss in more detail bellow.

$$\ket{\psi_0} = J\ket{00} = \cos\left(\frac{\gamma}{2}\right)\ket{00} +i\sin\left(\frac{\gamma}{2}\right)\ket{11}$$ 

note that the classical strategy basis is $$\{\ket{00}\leftrightarrow (C,C), \ket{01}\leftrightarrow  (C,D), \ket{10}\leftrightarrow  (D,C),\ket{11}\leftrightarrow  (D,D)\}$$. The players then apply local unitary operators to adjust the probability of defecting or cooperating. The local unitary is often times written as $$U(\theta,\phi)$$ where $$\theta,\phi$$ are parameters that correspond to how the players choose to adjust their states. 

$$U(\theta, \phi) =
    \begin{bmatrix}
    e^{i\phi} \cos\left(\frac{\theta}{2}\right) & \sin\left(\frac{\theta}{2}\right) \\
    - \sin\left(\frac{\theta}{2}\right) & e^{-i\phi} \cos\left(\frac{\theta}{2}\right)
    \end{bmatrix}$$


The update step can be written simply as the application of each player's unitary matrix $$U_i(\theta_i,\phi_i)$$ as applied to $$\ket{\psi_0}$$

$$\ket{\psi_1} \leftarrow (U_1 \otimes U_2)\ket{\psi_0}$$

Finally we apply $$J^\dagger$$ to bring the outcomes back into the classical strategy basis and take a measurement to determine the outcome. Each outcome corresponds with a classical payoff outlined an a table like that described above.

$$J^\dagger\ket{\psi_1} \xrightarrow[Measure]{} \ket{xy}, \quad x,y \in \{0,1\}$$

The affects of the infinite number of unitaries each player can apply vary and offer players classical strategies and new non-classical strategies that are not available within the classical setting. For example $$U(\pi,0)$$ corresponds with the bit flip operator $$X$$ which swaps the probabilities of cooperating and defecting. While $$U(0,0)$$ corresponds to the Identity matrix which does not change the players decision probabilities. Both of these actions are classical in nature and are available to players in a classical prisoner dilemma game. Notice that in both actions references above $$\theta=0$$. This gives us the generally fact that $$\theta$$ controls a players classical ability to adjust their personal decision probabilities, while $$\phi$$ introduces local phase which does not affect personal decision probabilities but instead can non-classically affects joint outcomes (i.e the shared environment). We provide a few examples bellow that reflect a number of these strategies. 

## Example 1: $$U(0,0)$$ at $$\gamma = 0$$

In this case we allow $$\gamma=0$$, which means that the decision probabilities of both players are not-entangled. This can be interpreted as disallowing any implicit communication between the two players while the game is in progress. Second we let $$U_1 = U_2 = U(0,0) = I$$, which implies that both players wish to make no changes to their decision probabilities. In this case the two players will chose $$(C,C)$$ 100% of the time since $$\gamma=0$$ defaulted the players to (C,C) and both players chose to stay the course. 

$$J\rightarrow \ket{\psi_0} = \ket{00}$$

$$(U_1 \otimes U_2) \ket{\psi_0} = \ket{00}$$

$$J^\dagger \ket{00} = \ket{00} $$

$$\implies P(00) = 1,\quad P(01) = P(10) = P(11) = 0$$

## Example 2: Phase sabotage at $$\gamma = 0$$

In this case we let $$\gamma=0$$ which means that the decision probabilities of both players are not-entangled. We also set $$\theta=0$$ and let $$\phi\not=0$$. This implies that the players wish to make no direct changes to their decision probabilities, but instead wish to induce some sort of change to the joint probability outcome. 

$$\ket{\psi_0} = \ket{00}$$

$$U_1 = U(0,0) = I, \quad U_2 = U(0, \pi/2) = \begin{bmatrix} i & 0 \\ 0 & -i \end{bmatrix}$$

$$(U_1 \otimes U_2) \ket{00} = i|00\rangle$$

$$J^\dagger\ket{\psi_f} = i|00\rangle$$

$$P(00) = 1, \quad \text{others} = 0$$

This example illuminates that there is no penalty for adding a phase when no entanglement is present. This shows that the phase $\phi$ has no strategic effect unless there is entanglement — like bluffing without an audience. Example 1 and 2 highlight that when $$\gamma=0$$ and there is not entanglement, the QPD reduces to a classical PD, where mixed strategies are allowed, but communication between the two parties during the course of the game is impossible. 

## Example 3: $$U(0,0)$$ at $$\gamma = \pi/2$$

In this case we allow $$\gamma=\frac{\pi}{2}$$ which means that the decision probabilities of both players are entangled (i.e the actions of the player 1 will impact the action player 2 choose to make and vice versa). A $$\gamma$$ of $$\frac{\pi}{2}$$ also defaults the players to a equal probability of achieving any of the 4 outcomes. Second we let $$U_1 = U_2 = U(0,0) = I$$, which implies that both players wish to make no changes to their decision probabilities.

$$J \ket{00} = \frac{1}{\sqrt{2}} (\ket{00} + i \ket{11})$$

$$U_1 = U_2 = U(0,0) = I$$

$$(U_1 \otimes U_2) \ket{\psi_0} = \frac{1}{\sqrt{2}} (\ket{00} + i \ket{11})$$

$$J^\dagger \ket{\psi_0} = \frac{1}{2}(\ket{00} - i\ket{01} + i\ket{10} + \ket{11})$$

$$ \implies P(00) = P(01) =  P(10) =  P(11) = \frac{1}{4}$$

## Example 4: Phase sabotage at $$\gamma = \pi/2$$

In this case we allow $$\gamma=\frac{\pi}{2}$$ which means that the decision probabilities of both players are entangled. Second we let $$U_1 = U(0,0)$$, which means that player 1 wishes to make no changes to their decision probabilities, whereas $$U_2 = U(0, \pi/2)$$

$$\ket{\psi_0} = \frac{1}{\sqrt{2}} (|00\rangle + i|11\rangle)$$

$$U_1 = U(0,0) = I, \quad U_2 = U(0, \pi/2) = \begin{bmatrix} i & 0 \\ 0 & -i \end{bmatrix}$$

$$(U_1 \otimes U_2) \ket{\psi_0} = \frac{1}{\sqrt{2}} (i|00\rangle - i|11\rangle)$$

$$J^\dagger \ket{\psi} = \ket{00}$$

$$P(00) = 1, \quad \text{others} = 0$$

The interaction between the two actions is more nuanced in this case. Since if $$U_2$$ had $$I$$ we would have had equal probabilities across the full result space like in example 3. However by adjusting $$\phi$$, player 2 was able to secretly shape the joint outcome to be (C,C). This models a player's ability to adjust the joint environment instead of just their own decision probabilities. This feature is unique to QPD and is inline with the features we wish to model in an adversarial signaling game. 

## Example 5: Strategic anticipation and covert betrayal at $$\gamma = \pi/2$$

$$\ket{\psi_0} = J \ket{00} = \frac{1}{\sqrt{2}} (|00\rangle + i|11\rangle)$$

$$U_1 = U(\pi, \pi/4), \quad U_2 = U(0, 0) = I$$

$$(U_1 \otimes U_2) \ket{\psi_0} = \frac{1}{\sqrt{2}} (|10\rangle - i|01\rangle)$$

$$\ket{\psi_f} = J^\dagger \left(\frac{1}{\sqrt{2}} (|10\rangle - i|01\rangle)\right)$$

$$P(10) \approx 1, \quad \text{others} \approx 0$$

Consider a case where Player 2 has established a pattern of naively applying $$U(0,0)$$ which maintains equal probabilities across the result space, but Player 1 anticipates this and strategically applies $$U(\pi, \pi/4)$$. Then player 1's action pushes the final state toward $$\ket{10}$$ (D, C) which maximizes Player 1’s payoff while punishing Player 2. Additionally note that unlike the $$\gamma=0$$ case, player 2 can't be certain that player 1 actively defected since the from their point of view the outcome was just "bad luck" since they agreed to an equal probability of each outcome. This type of action strategy is known as "covert betrayal" and offers a new dimension to the stratagem that the players can employ.

At this point note that while (QPD) only requires 4 output state, one may want to simulate a scenario where the players have more outcomes they can induce. To this end we can employ qudits which are qubits that encode more output states. We can also expand our qubit space to $$n$$ qubit $$\ket{\psi_0}$$ which would allow for $$2^n$$ possible outcomes. We intend to explore this expansion during my work with Red Hen Labs. We've described how the QPD framework allows players to take actions that change the shared environment along with their own personal states. We've also described cases where a player can adjust their action to exploit an action pattern they may have anticipated. This begs the question of how a player can both identify patterns in their opponents and determine whether the pattern represents an intentional deception or opportunity for exploitation. To that end we discuss a few approaches in literature that have been used to expand the QPD from a single round game to an iterative game that has the capacity to capture the features of the an adversarial signaling game.


Belief and Action Estimation
-----

The first task a player has after a round has come to an end is to determine the strategy their opponent may have used in order to track whether an exploitable pattern is emerging. This can be done by leveraging tools from classical optimization. Specifically a player can estimate $$U_2(\theta, \phi)$$ based on observed measurements by fixing their own unitary $U_1$ and iterating over candidate values of $$(\theta, \phi)$$ for $$U_2$.$ For each candidate the player can compute the candidate final state along with its corresponding measurement probabilities $$P_{ab}(\theta, \phi)$$.

$$\ket{\psi_f(\theta, \phi)} = J^\dagger (U_A \otimes U_B(\theta, \phi)) J \ket{00}$$


Next the player can repeatedly compute the following loss function for all candidate final states and optimize for $$(\theta^*, \phi^*) = \arg\min_{\theta, \phi} L(\theta, \phi)$$ using basic grid search, Bayesian optimization or even evolutionary optimization. 

$$L(\theta, \phi) = \sum_{ab} \left( P_{ab}(\theta, \phi) - P_{ab}^{\text{obs}} \right)^2$$

For example if the player 1 plays 10 rounds while using $$U(0,0)$$, and observe the following measurement frequencies:

$$P_{00}^{\text{obs}} = 0.1, \quad P_{10}^{\text{obs}} = 0.9$$

Then player 1 can sweep over candidate $$U_2(\theta, \phi)$$ and find that $$U_2$$ is likely $$U(\pi, \pi/4)$$, which strongly suggests the opponent is defecting with a phase twist, a known stealth betrayal tactic. Once a player has this information they can feed the inferred data into a reinforcement learning model in order to determine their next action $$(\theta',\phi')$$. This pipeline may induce interesting strategies such as rewarding honest opponents, testing cooperates with sudden "covert" phase perturbations and even detecting patterns in behavior that can be exploited. All of these features are ones that we sought to incorporate in order to effectively model an adversarial signaling game. Note however the variational quantum policy is a tool used in literature that may be worth investigating as an alternative to classically optimizing over the space of probability measures.



