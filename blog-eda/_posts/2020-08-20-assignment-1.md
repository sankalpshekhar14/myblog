---
layout: post
title:  "Assignment-1 - Experiencing Data in Heterogenous Systems"
date:   2020-08-20 
category: EDA
permalink: /:categories/assignment1
---
## Contents:
* [Objective](#objective)
* [The Mainframe](#the-mainframe)
    * [Introduction](#intro-mf)
    * [Mainframe Concepts](#concepts)
* [N-Tier Architecture](#n-tier)

***  

<br/>

## Objective

The objective of the assignment is to experience the real-world problem of data exchange between different generations of applications. In case of large organisations, different functions might be deployed on different systems, with these systems, often spanning across generations. For the smooth functioning of the organisation, it is important for these systems to communicate with each other and exchange data, without any problems.

With this in mind, we try to deploy three systems- **A Mainframe, An N-tier Architecture, and a Microservices Architecture.**

The mainframe will be used to compute **sin<sup>2</sup>$$\theta$$** and the n-tier architecture(*NoSQL + Java + Front End*) will compute **cos<sup>2</sup>$$\theta$$**.

Using the results from both the systems, the microservices architecture will test the hypothesis:

**sin<sup>2</sup>$$\theta$$ + cos<sup>2</sup>$$\theta$$ = 1.**

<br/>

## The Mainframe

### Introduction
 {:#intro-mf}

 Mainframes or Mainframe computers, are computers used generally by large organisations, for various critical applications, involving data processing in bulk numbers, like airline ticketing, bank transactions, etc.

 Mainframe computers are used for operations, were any **downtime** is *expensive and catastrophic*. They are known for **Reliability, Availability and Serviceablity(RAS)**. 

 They have high compute and memory, but are characterised by:

 * Redundant internal engineering, to ensure high reliability, and security.
 * Extensive I/O facilities
 * Backward Compatibility with old systems
 * High Degree of resource utilisation, leading to a high **throughput**.

 In contrast to supercomputers, which are built for high-performance computing, and have a high number crunching ability, mainframes are mainly built to handle large number of transactions at the same time, with the transactions being very simple operations. Supercomputers are measured with the metric **floating point operations per second(FLOPS)**, whereas mainframes are measured in **millions of instructions per second(MIPS)**.



