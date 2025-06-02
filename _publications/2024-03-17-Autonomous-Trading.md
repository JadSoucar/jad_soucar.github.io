---
title: "Autonomous Trading Using Deep Q Learning"
collection: publications
category: manuscripts
permalink: /publication/2024-03-17-Autonomous-Trading
excerpt: ' In this paper, we explore the application of Deep Reinforcement Learning (DRL) to the domain of autonomous equity trading, with a particular focus on the use of Deep Q Networks (DQNs) coupled with risk-sensitive loss objectives, to develop trading agents capable of navigating complex financial market conditions.'
date: 2024-03-17
#venue: 'Journal 1'
#slidesurl: 'http://academicpages.github.io/files/slides1.pdf'
paperurl: 'http://JadSoucar.github.io/files/RLTradingwithRisk_Soucar_Surana.pdf'
#bibtexurl: 'http://academicpages.github.io/files/bibtex1.bib'
#citation: 'Jad Soucar, Ninaad Surana. (2024). &quot;Autonomous Trading Using Deep Q Learning &quote;'
---
In this paper, we explore the application of Deep Reinforcement Learning (DRL) to the domain of autonomous equity trading, with a particular focus on the use of Deep Q Networks (DQNs) to develop trading agents capable of navigating the complex and dynamic landscape of the financial markets. We introduce three
variants of the DQN model; Vanilla DQN (V-DQN), Target DQN (T-DQN), and Double DQN (D-DQN). Our models incorporate a comprehensive set market indicators into the state space and several risk metrics into the reward function to guide the trading decisions towards not only profitability but also risk-adjusted returns. The risk metrics include the Sharpe Ratio, Sortino Ratio, and Treynor Ratio. We test each Q learning scheme outlined above with each risk metrics to determine the best trading agent. We find that most trading agents earn a percentage increase of around 6%-13%. After training, we find that incorporating the Sharpe ratio into the reward function produces the best return, and that the Double DQN algorithm is optimal across all risk metrics.
