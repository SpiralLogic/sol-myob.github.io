---
layout: post
title:  "Networking Advanced"
date:   2018-03-14 09:00:01 +1100
categories: networking amazon ec2 aws
tags: networking amazon ec2 aws
---

# Networking Advanced
Notes around networking advanced session held by JC and Parteek at MYOB.

#### Things that were covered
* **VPC** Virtual Private Cloud
* **Availability Zones** - The zones in which the aws instance will be available via VPC (virtual private cloud)
* **Multi Availability Zones** - When multiple instances are available from different zones to ensure that there is a higher availability through redundancy
* **Failure is the normal scenario** - with cloud infrastructure and networking failure isn't a matter of *if* and more a matter of *when*
* 172.31.0.0/16 , 17.31.0.0/20 are examples of subnet masks
* Subnets cannot span regions
* VPC is region specific, AZ is subnet specific
* NACL - Network Access Control List
* Public & Private ACL within AZs
* To find the routing table in osx and linux: netstat -rn
* Routing table rules are parsed in order, with the final catach-all being 0.0.0.0/0
* **ELB** Elastic Load Balancer - allows balancing of instances across regions and availability zones to allow higher availability and throughput speeds
