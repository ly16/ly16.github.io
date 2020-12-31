---
layout:     post
title:      Network Protocols
subtitle:   What happened when you enter an url?
date:       2020-12-31
author:     Clover
header-img: img/systemDesign.jpeg
catalog: true
tags:
    - System Design

---

### Basic concepts
- Client: sends/requests data to server
- Server: returns data to the client
- port: 16,000 ports in one machine eg HTTP 80, HTTPS 443 port#

### Try examples
#### Mock client and server
> Send data to local machine port `nc 127.0.0.1 8081` (terminal1)
> Listen data from local machihe  port `nc -l 8081` (terminal1)
> You can send data from the first terminal

#### Find IP address of a public url
> find IP address in Mac `dig google.com`


### What happened when you enter an url to your browser
browser(client) -> DNS query(IP address) -> send HTTP request(send data: packet, source IP address) -> Google.com(server) -> reponse HTML/CSS to clients



