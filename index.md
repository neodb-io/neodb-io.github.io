---
layout: default
title: NeoDB Database Platform Introduction
---

# NeoDB Database Platform

## 1. Vision
We want to build an <b>all-in-one database platform</b> to help small or medium sized orginization managing their data and providing high quality services, with <b>minimal cost</b>.


## 2. Background
- Storage systems cost too much resources these years and most of the cost are just waste of money
- Modern hardware development is <b>much faster</b> than storage algorithms & data structures, we want to re-design them
  - Barely see any KV system can use the full advantage of NVMe SSD's bandwidth
  - Persistent main memory provides near DRAM latency and much higher bandwidth than NVMe SSD
- User experience (e.g. WebUI) is ignored for decades, most users have to development their own management panal, that's not so good for non-technical companies or organizations.


## 3. Introduction

NeoDB is a <b>VERY LONG TERM</b> product and will be released module by module.

NeoDB aims to build an cost efficient and high performance data <b>mangement & monitoring & analysis </b> platform.

NeoDB includes three top layer components (<b>each component could be used individually</b>):

- WebUI (Not Started)
  - <i>Data management, monitoring and analysis</i>
- Data Modeling System (Not Started)
  - <i>High level abstraction of the KV storage layer that fits into NoSQL or SQL usage</i>
- Data Storage System (Under Development)
  - <i>A set of core KV storage systems for different purposes</i>
  - <i>Including columar store and row store engines</i>

## 4. Modular Design for Data Storage System
Users can choose any module to fit their special cases, e.g. use a <i><b>NeoDB for NVMe SSD KV</b></i> to enable high density( > 60TB) & high performance & low cost single server storage.

<b>Module List:</b>
- <b>NeoDB for NVMe SSD KV</b>
  - Leverage NVMe SSD's high bandwiidth and great IOPS into modern storage system
  - Sequential write & background GC(not compaction) & extremly memory efficient index design
  - Consistency & greate performance with over 60TB SSD & 1TB DRAM per server
- <b>NeoDB for IoT</b>
  - Multi active write point with acceptable data loss
  - Auto sharding & repairing & migrating
  - Extremely fast insertion and low cost
- <b>NeoDB for Persistent Memory KV</b>
  - Near memory performance with much lower cost and data persistent ability
  - Fast recovery (thanks to Optane's great performance)
- ...

## 5. Architecture
<img width="100%" src="/images/architecture.png"/>

## 6. Milestones & Plan

Current we are working on all storage modules:

### 6.1. NeoDB for IoT
Ongoing

<!-- - [ ] ...
- [ ] ...
- [ ] Basic WebUI integration
- [ ] Command line tool for quick test drive
- [ ] Refactor meta server by using raft protocal
- [ ] First workable version release
- [ ] Auto sharding & migirating
- [ ] Meta server first version without raft implementation
- [x] Columar storage engine for time series data first version -->

### 6.2. NeoDB for NVMe SSD KV
TODO

### 6.3. NeoDB for Persistent Memory KV
TODO

## 7. License
TODO
