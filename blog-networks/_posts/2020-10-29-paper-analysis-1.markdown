---
layout: post
title:  "Analysis of Paper: Toward Packet Routing with Fully-distributed Multi-agent Deep Reinforcement Learning"
date:   2020-10-29 
category: Networks
tags: Packet-Routing, DeepRL, Q-learning
---
## Contents:
* [Introduction](#introduction)
* [Traditional Routing Algorithms](#traditional)
* [RL-based Routing Algorithms](#rl-routing)
* [Q-Routing](#q-routing)
* [DQN](#delay)
* [Layers of a Network](#layers)
* [Attack on Networks](#attack)

***  

<br/>
You can find the link to the paper [here]().

### Introduction
{: #introduction}

This paper talks about packet routing, which is one of the most challenging problems in the field of computer networking. This problem gets even more challenging when the size of the network is scaled, and there is an absence of a centralised or coordinated service provider. As the packet is transmitted from source to destination, the routers at each hop should decide to which neighbour should they send their packet, in order to minimize the delivery time, subject to other constraints.

In a large and dynamic network, it is necessary for routers to adapt and update their forwarding policies on a regular basis, in order to account for congestion, link failure and various other situations. The paper uses Reinforcement Learning based approach to packet routing, an algorithm that naturally fits the role of adaptive routers, which can explore various routes, and over time, learn the optimal* forwarding policy for routing packets.

A number of papers in RL-based routing are mentioned, a list of it given below. A comparison between traditional routing algorithms and rl-based algorithms are discussed. **Q-routing** is one of the first RL-based routing algorithms used in networks. Certain modifications have been made to it over time, but they are all based around q-routing.

### Traditional Routing Algorithms
{: #traditional}

In traditional routing, the shortest path based approaches have been mentioned, namely:
* Djikstra's Algorithm 
* Bellman-Ford Algorithm

The definition of shortest path may vary, either the number of hops, or transmission delay. This approach is very intuitive, as it makes the assumption that **between two nodes, the shortest path takes the least amount of time to transmit the packet.** This assumption fails in large networks and high traffic, where the packet might spend enormously large amount of times on router queues, often taking longer than other longer, yet less congested paths. 

**Backpressure** is another approach that routes packets using **congestion gradients**. In simpler words, it utilises the differential of queue backlogs of the current router and its neigbours, as a pressure to drive packets. A drawback of this approach is the poor delay performance in case of networks with light load, as there is not enough pressure to drive the packets, and they choose long and inefficient routes.

### RL-based Routing Algorithms
{: #rl-routing}

The first RL-based approach was **Q-routing**, which is a variant of Q-learning.

There are two different approaches in RL-based routing:

1. #### Single-Agent Approach
In single-agent approach, the network controller is treated as a central agent which can observe the global information of the network and control the packet transmission at each router. Both the learning and execution are centralised.

2. #### Multi-Agent Approach
In multi-agent learning, each router in the network is treated as a single agent which can observe partial environment information and take actions according to its own routing policy.

Single-agent approaches are hard to be applied in a large network. The centralised learning controller is usually unable to gather local environment changes in different sections of the network.

A distributed, multi-agent approach is more suitable, as it allows each router to capture details of its neighbours locally, and also helps it to adapt to different constraints.

### Q-Routing









