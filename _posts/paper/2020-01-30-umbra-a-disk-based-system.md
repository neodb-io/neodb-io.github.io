---
layout: post
title: "[CIDR ‘20] Umbra: A Disk-Based System with In-Memory Performance"
category: paper
tags:
    - "NVMe SSD"
    - "KV"
    - "HyPer System"
    - "Pointer Swizzling"
    - "Cache Manager"
---


### 1. About the Paper
- [http://cidrdb.org/cidr2020/papers/p29-neumann-cidr20.pdf](http://cidrdb.org/cidr2020/papers/p29-neumann-cidr20.pdf)
- The first author <i>Thomas Neumann</i> is a famous database researcher who founded HyPer system which was acquired by tableau


### 2. WHY
- DRAM is relatively expensive than NVMe SSD (20~40 times)
- Latest NVMe SSD can archieve 3.5GB/s sequential read per disk
  - The paper didn't mention latency, but AFAIK, modern NVMe SSD (SLC) can archieve about 30us 4K read/write latency.

### 3. Main Ideas
- Use a carefully designed <b>buffer manager</b> that combines low-overhead buffering with variable-size pages.
- A fixed-size page would make the buffer manager easier to build but also makes users harder to use.
- This paper is mainly talking about the buffer manager

<img src="/images/paper/umbra-1.png" width="100%" >

### 4. Key Concepts
#### 4.1. Buffer Manager
- Database pages are organized in <i>size classes</i> and 64KB is the smallest page size.
- Thus all pages will be located directly into proper page fragments.
- Buffer manger uses seperate mmap for each <i>size classes</i>
- Open Channel for better storage control is mentioned but not yet implemented

#### 4.2. Pointer Swizzling
- Pointers are encoded to indentify whether target pages are loaded into memory or still on-disk.
- If target page is on disk, then it will use 6 bits of the pointer to identify its <i>size class</i>.

#### 4.3. Versioned Latches


#### 4.4. Index & Data Store


### 5. Conclusion
- This paper provides a concept of how to utilize the power of NVMe SSD