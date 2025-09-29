
### *Wireshark Packet Analysis Summary*
Wireshark is a free and open-source tool used for network analysis. You can think of it as a "network traffic microscope" that captures data packets traveling to and from your computer and allows you to inspect them in great detail.

**1. Objective**

The objective of this task was to perform a hands-on network packet analysis using Wireshark to understand how fundamental internet protocols function and to gain protocol awareness.

**2. Methodology**

* *Installation & Setup:* The Wireshark application was downloaded and installed on a computer.
* *Packet Capture:* A live network capture was initiated on the active Wi-Fi interface.
* *Traffic Generation:* To generate network traffic for analysis, a web browser was used to visit the website www.youtube.com.
* *Capture Duration:* The capture ran for over one minute to ensure a sufficient amount of data was collected.
* *Capture Termination:* The capture was stopped to begin the analysis.
* *Filtering:* A display filter (http or tcp or dns) was applied to isolate the packets related to the protocols of interest, making the analysis more focused.

**3. Findings and Protocol Identification**

The packet capture revealed several different protocols, demonstrating a clear hierarchy and sequence of network communication.

* *DNS (Domain Name System):*
    * *Role:* The DNS protocol was the first step in the network conversation. It served to translate the human-readable domain name www.youtube.com into its corresponding numerical IP address.
    * *Findings:* The capture showed a DNS query packet originating from my computer to a DNS server, followed by a DNS response packet from the server that provided the correct IP address.

* *TCP (Transmission Control Protocol):*
    * *Role:* TCP's primary role was to establish a reliable and orderly connection for the data transfer. It acts as a foundation for higher-level protocols.
    * *Findings:* The TCP packets clearly showed the three-way handshake:
        1.  *SYN:* My computer sent a Synchronize packet to the YouTube server.
        2.  *SYN-ACK:* The server responded with a Synchronize-Acknowledge packet.
        3.  *ACK:* My computer sent a final Acknowledge packet, completing the connection setup.

* *TLS (Transport Layer Security) & OCSP (Online Certificate Status Protocol):*
    * *Role:* Since www.youtube.com is a secure website (HTTPS), the HTTP traffic was encrypted. The TLS protocol was responsible for creating this encrypted channel over the TCP connection. The OCSP protocol was also observed, used to verify the website's security certificate in real-time.
    * *Findings:* After the TCP handshake, the capture showed a series of TLSv1.2 packets, representing the secure connection setup. Within this process, the OCSP protocol confirmed the validity of the server's certificate.

*4. Summary of Findings*

This hands-on exercise successfully demonstrated the fundamental principles of network communication. The capture provided a clear, step-by-step view of how a simple action like browsing a website involves a complex series of layered protocol interactions. The protocols, including *DNS* for name resolution, *TCP* for connection reliability, and *TLS* for data encryption, all worked in harmony to facilitate the network conversation.

By analyzing the captured packets, I was able to observe and confirm these core networking concepts, fulfilling the requirements of the task.
