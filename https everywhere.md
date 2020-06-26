#  Microservices Security Design Patterns

## Use Https 
HTTPS has an official name: Transport Layer Security (a.k.a., TLS). It’s designed to ensure privacy and data integrity between computer applications. [How HTTPS Works](https://howhttps.works/) is an excellent site for learning more about HTTPS.
Https Addresses there security needs

 - Privacy
 - Integrity
 - Identification
 To use https one must need certificate
	 - [Let's Encrpyt](https://letsencrypt.org/)
	 
	> Let’s Encrypt launched on April 12, 2016 and somehow transformed the Internet by making a costly and lengthy process, such as using HTTPS through an X.509 certificate, into a straightforward, free, widely available service. Recently, the organization announced it has issued one billion certificates overall since its foundation and it is estimated that Let’s Encrypt doubled the Internet’s percentage of secure websites
	
	- Let’s Encrypt recommends you use [Certbot](https://certbot.eff.org/) to obtain and renew your certificates
     >**Certbot** is a free, open-source software tool for automatically using Let’s Encrypt certificates on manually-administrated websites to enable HTTPS. The Electronic Frontier Foundation (EFF) created and maintains Certbot.

### How to use a certificate with Spring Boot
#### src/main/resources/application.yml
``` yml
server:
  ssl:
    key-store: classpath:keystore.p12
    key-store-password: password
    key-store-type: pkcs12
    key-alias: tomcat
    key-password: password
  port: 8443
```
####

<!--stackedit_data:
eyJkaXNjdXNzaW9ucyI6eyJuNUhTUHdPSGgzOUtpRFE2Ijp7In
N0YXJ0IjozNTAsImVuZCI6MzUwLCJ0ZXh0IjoiTGlzdCBpdGVt
In19LCJjb21tZW50cyI6eyJNVjFjTDAybk9tMVgxbWJzIjp7Im
Rpc2N1c3Npb25JZCI6Im41SFNQd09IaDM5S2lEUTYiLCJzdWIi
OiJnaDoxMjE4NTcwMiIsInRleHQiOiJQcml2YWN5IiwiY3JlYX
RlZCI6MTU5MzE0ODE4MTg2MX19LCJoaXN0b3J5IjpbOTMyMTcw
NDcxLDk2MzM4NDk2MF19
-->