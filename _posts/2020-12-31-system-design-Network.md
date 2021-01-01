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
- TCP/IP model layers
     <figure>
      <img src="/img/tcpip5layer.png" alt="Image" />
    </figure>
     <figure>
      <img src="/img/layerdefinition.jpg" alt="Image" />
    </figure>
    
   - Add header from the higher leyer to the lower layer
    <figure>
      <img src="/img/addheader.png" alt="Image" />
    </figure>


- Process of data transmission
    <figure>
      <img src="/img/tcpiptransdata.jpeg" alt="Image" />
    </figure>
    - From higher layer to lower laryer in sender, From lower layer to higher layer in receiver
     <figure>
      <img src="/img/datatrans.png" alt="Image" />
     </figure>
    

- Client: sends/requests data to server
  - A single machine can be both client and server at the same time. eg. A single machine could acts as a aserver for end users and client for a database.
    
- Server: returns data/service to the client, listening for incoming network calls

- port: 16,000 ports in one machine eg HTTP 80, HTTPS 443 port#

- IP address: Address that each machine connected to the public Internet. a.b.c.d (four numbers are all (0, 255))
  - 127.0.0.1 is to localhost, 192.168.a.b is to private network, have 192.168 prefix, internal network.

- IP: Internet protocal, IP address. IP packet: stored in bytes
  - IP header: 
    
    | source IP address, destination address, total size of packet, internet IP version IPV4 or IPV6 | Payload: data to send(2^16 bytes) so we need multiple ip packets (TCP) for large files |
  
- TCP: transmission control protocal. Send IP packet in order. Error free way, resend if incorrect.  Build on top of IP.
  - Allow for ordered, reliable data delivery between machines over the public internet by connection.
  - TCP structure: 
        
    | IP header | TCP header | data|
        
  - TCP connection, handshake, timed out, end the connection, sockets to applications
  
- HTTP: HeperText transfer protocol. request-response paradigm. More business logical than IP and TCP. Build on top of TCP.
  - http request: host, port, method(get, put, post, delete), path, headers, body, cookie
  - http responces: statusCode, headers, body
  - Difference between POST and PUT?
     <figure>
      <img src="/img/putandpost.png" alt="Image" />
    </figure>


  


### Try examples
#### Mock client and server
> Send data to local machine port `nc 127.0.0.1 8081` (terminal1)
> Listen data from local machihe  port `nc -l 8081` (terminal1)
> You can send data from the first terminal

#### Find IP address of a public url
> find IP address in Mac `dig google.com`

#### Send/retrive data to servers
> `curl localhost:8080/world` 
> default http, get


### What happened when you enter an url to your browser
[Video reference](https://www.youtube.com/watch?v=dh406O2v_1c)

browser(client) -> DNS query(IP address) -> send HTTP request(IP packet) -> Google.com(server) -> reponse HTML/CSS to clients

1. Initial typing: auto complement,  history and local cache
2. Url parsing: url or search words
3. Find protocol: HTTPS 443 (default) or HTTP 80

4. DNS lookup (domain name server): IP address, local cache or DNS over HTTPS
    - DNS is UDP server, send packet, send to router via to NAT gateway, get response from ISP(Internet Service Provider ) of IP address of google.com
5. TCP connection: 3 way handshake to build connection, go through many routers
    - Client Hello, server Hello, TLS protocol, Client key exchange, Server key exchange
6. GET request: Cookie together with the get request, send the header, response with the HTML web page body
   - http request: host, port, method(get, put, post, delete), path, headers, body, cookie
   - passowrd and username: token, store in cookie. Check whether is the correct person to log in.
   - http responces: statusCode, headers, body
7. HTML parsing: content-type html, image, html, js, css




