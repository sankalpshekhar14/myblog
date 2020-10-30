---
layout: post
title:  "Assignment-1 - Experiencing Data in Heterogenous Systems"
date:   2020-08-20 
category: EDA
permalink: /:categories/assignment1
---
***

## Contents:
* [Objective](#objective)
* [The Mainframe](#the-mainframe)
    * [Introduction](#intro-mf)
    * [Mainframe Concepts](#mf-concepts)
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

 96 of the world's 100 major banks, and a majority of the airlines today, still use mainframes for their operations. IBM is the primary manufacturer of these systems. With a very high reliability and stability, **mean time between failures(MTBF)** is in decades.
### Mainframe Concepts
{:#mf-concepts}

A mainframe computer can run multiple instances of an operating system at the same time, independently. These **virtual machines**, allow applications to run as if they are on a physically separated computer. While **virtualisation** is very popular now, mainframes first pioneered this idea in the '60s.

In contrast to distributed systems, which are highly decentralised in terms of compute and storage, a single mainframe can replace multiple functioning services available in conventional servers.

Apart from the central cores, there are various **System Assist Processors(SAP)** attached to it, which help to move data efficiently around the entire mainframe system. 

More about mainframes can be found [here](#).

### Building the System

#### Setting Up the Mainframe 

I used Hercules, an open-source emulation software for mainframe systems, for the environment. I installed the x3270 emulator, along with a Free BSD licensed version of IBM MVS 3.8.

#### Plan of Action

#### Code 

#### Review and Improvements


<br/>

## The N-tier Architecture
{:#n-tier}

### Introduction 

### Concepts

### Building the System

<br/>

## Microservices
{:#micro}

### Introduction 

### Concepts

### Building the System



