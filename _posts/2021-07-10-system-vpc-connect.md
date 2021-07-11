---
layout:     post
title:      Vpc connection
subtitle:   Vpc direct connect, Vpc peering, Vpc private link (endpoint)
date:       2021-07-10
author:     Clover
header-img: img/systemDesign.jpeg
catalog: true
tags:
    - System Design

---

### Basic concepts
- AWS Direct Connect

[AWS Direct Connect is a cloud service solution that makes it easy to establish a dedicated network connection from your premises to AWS.](https://aws.amazon.com/directconnect/?nc=sn&loc=0)


- AWS Vpc Peering

[A VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them using private IPv4 addresses or IPv6 addresses.](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html)

- AWS private link

[Establish private connectivity between VPCs and services hosted on AWS or on-premises, without exposing data to the internet.](https://aws.amazon.com/privatelink/?privatelink-blogs.sort-by=item.additionalFields.createdDate&privatelink-blogs.sort-order=desc)
  


### Main differences
##### VPC Endpoints vs. VPC Peering
[What Are the Differences Between VPC Endpoints and VPC Peering Connections?](https://support.huaweicloud.com/intl/en-us/vpcep_faq/vpcep_04_0004.html)
- limitation of vpc peering:

[The maximum quota is 125 peering connections per VPC](https://docs.aws.amazon.com/vpc/latest/userguide/amazon-vpc-limits.html)

##### AWS Direct connect vs. VPC peering
https://stackoverflow.com/questions/52871912/how-do-aws-direct-connect-and-vpc-peering-differ


