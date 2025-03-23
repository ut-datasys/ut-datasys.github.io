---
layout: default
title: Tigon 
description: A distributed transactional database on CXL memory  
img: /assets/img/db.jpg
category: Data Systems on Modern Hardware  
uselink: No 
---

#### Pasha: An Efficient, Scalable Database Architecture for CXL Pods  
<hr>

#### Abstract
<div style="text-align: justify; margin-bottom: 20px;">
Memory connected via Compute Express Link (CXL) presents a new
opportunity for building efficient and scalable databases. A CXL Pod
is a small number of independent hosts connected via CXL to shared
memory (termed CXL memory). A small part of the CXL memory is
hardware-cache-coherent across hosts. This paper proposes Pasha,
a new database architecture for the CXL Pod, that aims to efficiently
leverage the fast synchronization enabled by the hardware-cachecoherence of CXL memory and the low latency and high bandwidth
of local DRAM in each host. To achieve this goal, Pasha divides
and stores data into partitions, with each partition owned by a
single host, and a shared region that every host has access to. Then,
Pasha uses CXL memory to efficiently synchronize concurrent
accesses to the shared region across hosts and stores each partition
of data in local DRAM to leverage its low latency without crosshost synchronization overhead. In addition, Pasha ensures that
each host completes its transactions by directly reading or writing
data in either its own partition or the shared region, circumventing
multi-host transactions and two-phase commit (2PC). Pasha obtains
the best of partition-based distributed databases and single-node
shared-memory databases; preliminary results show it outperforms
both architectures.
</div>

#### Publication

[Pasha: An Efficient, Scalable Database Architecture for CXL Pods](https://dx-tang.github.io/paper/Pasha-CIDR25.pdf), CIDR 2025
