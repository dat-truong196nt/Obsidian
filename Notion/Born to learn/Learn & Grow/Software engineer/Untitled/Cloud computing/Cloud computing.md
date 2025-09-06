---
Created: 2022-06-24T09:29
---
Cloud computing:  
+ On-demand self-service: provision capabilities on demand without human interaction.  
+ Broad network access: everything is available over the internet.  
+ Resource pooling: be able to specify the high-level location, resources as a pool to serve multiple consumers with a multi-tenant model, data is isolated.  
+ Rapid elasticity: Rapid provisioned and released, unlimited resources.  
+ Measured service: Resource usage can be monitored, controlled, reported, and billed  
  
XaaS: X as a Service  
+ A cloud service model.  
  
  
  
YAML:  
+ Has key-value pair, list, dictionary type.  
+ Used for configuration.  
JSON:  
+ Has key-value pair, array, object type.  
+ Used for configuration and many others.  
  
Encryption:  
- Approaches: encryption at rest and encryption in transit.  
- Concept: plain text + key -(algorithm)→ ciphertext.  
- Symmetric encryption: Same key for encoding and decoding.  
- Asymmetric encryption:  
+ A pair of a public key and a private key is generated.  
+ Receiver will send the public key to the sender to encrypt data.  
+ Only the receiver holds the private key and can decrypt data.  
+ Harder to implement in comparison to the symmetric key.  
+ Private key is used to sign the message which can be validated by the public key (authorize)  
→ Real-life use case: Asymmetric key is used to transfer symmetric key.  
- Steganography: Hiding messages inside a text, images, etc  
  
Networking:  
OSI model:  
- Layer 1:  
+Define how to transmit and receive **RAW bit stream** (voltage level, timing, rates, distance, modulation) via an electrical shared medium.  
+ Its data is broadcast to all devices via **HUB**.  
- Layer 2:  
+ provide the **frame** with a dedicated **MAC address** for each network card interface.  
+ Provide **control access** (Build frame (2) → Check carrier (signal) (2)(1) → Transmit (1) → Receive (1) → Decode (2)).  
+ **Switch** will keep a Map(MAC, port) to redirect the message.  
+ ET: EtherType: Which protocol is used in layer 3?  
+ Must use the same protocol (diff frame blueprint) to connect 2 networks with only work on layer 2.  
- Layer 3:  
+ Benefits: when going to the internet, the source and destination public IP address is still the same, while MAC is changed due to the point-to-point connection on layer 2. Each router has a routing table that works with the subnet to produce an end2end connection.  
+ Route tables can be statically populated or use BGP(border gateway protocol) to communicate with route tables.  
+ ARP: Ask who has this IP to all MAC addresses → The machine that has this address will respond with its MAC.  
+ **Router** will deliver the message.  
- Layer 4:  
+ Allow multiple apps to transmit at the same time, control orders, dropped packets.  
+ TCP segments are encapsulated inside IP packets. TCP contains source/destination port, sequence number, ACK, window (how many bytes received between ACKs; ones reach, the sender will pause until get ACK), checksum, urgent pointer (for priority processing).  
+ Stateless connection: Doesn’t understand the state of the connection, needs 2 rules for outbound and inbound connection (NACLs)  
+ Statefull connection: When allow the outbound, the inbound is implicity allowed (Security Group).  
- NAT - only for IPv4:  
+ Translate private IPv4 addresses to public ones.  
+ Static NAT (1-1), Dynamic NAT (n-m)(using temp static NAT when needed), Port NAT (n-1)(gen ephemeral port to use same public IP address) ~ (private-public).  
+ NAT table: Mapping (private IP + Port → public IP + Port).  
- DDOS:  
+ Distributed Denial of Service.  
+ Overload website.  
+ IP is distributed.  
+ Application attach: HTTP request, Protocol attach: 3-way handsake with spoof IP, Volumetric: Send millions of DNS requests to the domain of App.  
- SSL:  
+ server will send the service certificate to the client to verify itself  
+ Client will trust the public CA (Certificate Authority) to verify the certificate of the server.  
- Hashing:  
+ md5 (collision), sha2-256 (more hash length, more trust).  
- Digital signatures:  
+ Integrity (What): Send the data and its hash → Data can’t be altered  
+ Authenticity (Who): Sign the hash with a private key → Hash is authorized.  
  
  
  
- If you’re using a specific layer, the underlining layers just work as an abstract level.  
- On the sender, the package will be wrapped from the high layer. On the receiver, the package will be unwrapped from layer 1.  

![[Untitled.png]]

- IAM role: grand access for an uncertain number of services, external access  
- IAM: Manage identities, authenticate, authorize  
- AccessKeys: <2 for 1 user, IAM user only.