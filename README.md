Cybersecurity Incident Report

 Identifying the type of attack that may have caused this network interruption

One potential explanation for the website's connection timeout error message is: After confirming a large number of TCP SYN requests coming from an unfamiliar IP address (203.0.113.0), the web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. This is a SYN flood DoS attack, which is causing the connection timeout error for legitimate users. I suspect the web server is under DoS attack.

 Too many TCP SYN requests coming from IP address (203.0.113.0) flooded the server (192.0.2.1) and not completing the handshake with the server. Thereby exhausting the server resources.

 This is SYN Flood attack, crashing the server resources and the real web user could not perform normal activities on it.

 When website visitors try to establish a connection with the web server, a three-way handshake occurs using the TCP protocol. 
1. The visitor device established a request to the server with the first handshake SYN 

2. The server established the connection by sending back SYN/ACK 

3. And the visitor acknowledge the response by the server the third handshake ACK

A malicious actor sends a large number of SYN packets all at once, The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. Thereby crashing the server, leading to “connection timeout”

 The logs indicate SYN packets from 203.0.113.0:54770 to 192.0.2.1:443 with no final ACK. This means half-open connections. It affects the server by filling its queue, exhausting memory, so it cannot serve real users and website shows timeout.




