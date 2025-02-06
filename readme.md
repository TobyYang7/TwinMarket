# TwinMarket: A Scalable Behavioral and Social Simulation for Financial Markets

<mark style="font-size: 1.5em;">**NOTE: We will update our code soon!**</mark>


    
![overview](./src/TwinMarket.jpg)

## Overview

**TwinMarket** is a novel multi-agent framework that leverages Large Language Models (LLMs) to simulate socio-economic systems, with a particular focus on financial markets.  It models individual investor behaviors, their social interactions, and the emergent phenomena that arise from these interactions.  Built upon the **Belief-Desire-Intention (BDI)** framework, TwinMarket realistically captures the cognitive processes and behavioral biases of agents, enabling the study of complex market dynamics such as bubbles, crashes, and volatility clustering.  The framework bridges the gap between micro-level individual decisions and macro-level market outcomes.

## Key Features

1. **Real-World Alignment**: The framework is grounded in established behavioral theories and calibrated with real-world data, ensuring realistic human behavior modeling.
2. **Dynamic Interaction Modeling**: TwinMarket captures diverse human behaviors and their interactions, particularly in the context of information propagation and social influence.
3. **Scalable Market Simulations**: The framework supports large-scale simulations, allowing researchers to analyze the impact of group size and interaction complexity on market behavior.

## Framework Components

### Micro-Level Simulation: Individual Behaviors

*   **BDI Framework**: Agents are modeled using the **Belief-Desire-Intention** framework, structuring their decision-making into:
    *   **Belief**: Represents the agent's understanding of the market.
    *   **Desire**: Captures the agent's objectives or preferences.
    *   **Intention**: Defines the concrete actions the agent executes.
*   **Behavioral Biases**: Agents exhibit realistic behavioral biases (overconfidence, loss aversion, herding, etc.), influencing their trading decisions and contributing to market heterogeneity.

### Macro-Level Simulation: Social Interactions

*   **Social Network Construction**:  Agents interact within a dynamic social network.  Connections between agents are based on the similarity of their trading behaviors, reflecting the idea that individuals with similar trading patterns are more likely to influence each other. A time decay factor is used so that more recent trades have more impact on the social network structure.
*   **Information Propagation**:  The framework models how information (news, rumors, opinions) spreads through the network.  This includes mechanisms for:
    *   **Information Aggregation**:  Agents receive information from their social network connections, with a focus on relevant and highly-engaged content.
    *   **Opinion Leaders**:  The emergence of influential agents who disproportionately shape market sentiment.
    *   **Echo Chambers and Polarization**:  The formation of groups with divergent beliefs, particularly under conditions of biased or extreme information.

### Data Sources

![data](./src/data.png)

*   **Real-World Data**: TwinMarket integrates:
    *   **Real User Profiles**: From Xueqiu (a Chinese social media platform for investors).
    *   **Transaction Details**: Also from Xueqiu.
    *   **Stock Data**:  From CSMAR (China Stock Market & Accounting Research Database), focusing on the SSE 50 index (50 largest and most liquid A-share stocks).
    *   **News Articles and Announcements**: From Sina Finance, 10jqka, and CNINFO.

*   **Data Preprocessing**: Create a joint distribution based on real user data.

## Experimental Results

### Information Propagation

![data](./src/vis6.png)

*   **Opinion Leaders**:  Simulations reveal the emergence of opinion leaders who exert significant influence on the network, shaping market sentiment and trading behaviors.  Their posts receive more engagement and drive information diffusion.
*   **Intimation & Polarization**: High-degree users receive more upvotes, and the network's adjacency matrix shows clusters of trading similarity.

![data](./src/vis2.png)

*   **Behavioral Polarization**:  Exposure to different information signals (particularly rumors) leads to the formation of distinct groups with divergent beliefs and trading strategies.  This polarization can increase market volatility and create self-reinforcing feedback loops.
*   **Belief Divergence:** Rumors lead to a divergence in user beliefs, and the formation of distinct echo chambers.
*   **Trading Volatility:** Rumor makes user more tend to sell, which leads to significant increase in sell/buy ratio.
*   **Market Turbulence:** Rumors makes the market suffer a sharp decline.

### Market Dynamics

![data](./src/vis4.png)

TwinMarket successfully replicates key **stylized facts** of financial markets:

*   **Fat-tailed Return Distributions**:  Extreme price movements occur more frequently than predicted by a normal distribution.
*   **Volatility Clustering**:  Periods of high volatility are followed by periods of high volatility, and vice versa. Market fluctuations exhibit temporal dependencies.
*   **Leverage Effect**:  Negative returns are correlated with increased future volatility, highlighting asymmetries in market behavior.
*   **Volume-Return Relationship**:  Trading volume is positively correlated with price changes,  illustrating the impact of liquidity on market dynamics.

Additionally, the framework reveals **emergent group behaviors** that are difficult to capture using conventional agent-based models. These include **self-fulfilling prophecies**, where collective expectations drive market trends, and **information cascades**, where traders rely on perceived consensus rather than fundamental analysis. Such emergent properties highlight TwinMarket’s capacity to bridge **micro-level agent interactions with macro-level market phenomena**, offering a robust and adaptive simulation environment for studying financial systems.

## Scalability

![price_index_plot.png](./src/price_index_plot.png)

TwinMarket is designed to scale to large populations, with simulations involving up to **1,000 agents**. The framework maintains realistic market dynamics even at larger scales, providing a robust platform for studying complex socio-economic systems.

## How to Cite

If you use TwinMarket in your research, please cite the following paper:

```bibtex
@misc{yang2025twinmarketscalablebehavioralsocialsimulation,
      title={TwinMarket: A Scalable Behavioral and Social Simulation for Financial Markets}, 
      author={Yuzhe Yang and Yifei Zhang and Minghao Wu and Kaidi Zhang and Yunmiao Zhang and Honghai Yu and Yan Hu and Benyou Wang},
      year={2025},
      eprint={2502.01506},
      archivePrefix={arXiv},
      primaryClass={cs.CE},
      url={https://arxiv.org/abs/2502.01506}, 
}
```
