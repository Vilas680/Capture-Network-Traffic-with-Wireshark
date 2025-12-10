📡 Wireshark Network Traffic Capture

📝 Objective

The goal of this task is to capture and analyze network traffic using Wireshark.
We specifically focus on:

Monitoring live network packets
Filtering HTTP/TCP traffic
Understanding packet structure (Ethernet → IP → TCP → Application Layer)

🔧 Tools Used

Wireshark 4.x
Network protocol analyzer for capturing and inspecting packets in real-time.

Steps Performed

1️⃣ Launched Wireshark

I opened Wireshark and selected the Wi-Fi interface (because I was connected to the internet through Wi-Fi).

The live graph shows active packets moving.

2️⃣ Started Live Capture

Clicked on the Wi-Fi interface, then clicked Start Capturing Packets.

A large number of packets were captured, including:

TCP traffic

QUIC encrypted traffic

HTTP requests

Local network communication

3️⃣ Applied Filters to Focus on Useful Traffic

To filter meaningful packets, I used:

🔍 Filter for HTTP traffic
tcp.port == 80
This shows packets related to websites using HTTP (port 80).

4️⃣ Analyzed Packets

I double-clicked individual packets and inspected:

📌 Packet Breakdown

Each packet had the following layers:

🔹 1. Ethernet II Layer

Shows MAC addresses:

Source: Your device’s network adapter

Destination: Router or remote server

🔹 2. IP Layer

Shows:

Source IP

Destination IP

TTL

IP version (IPv4/IPv6)

3. TCP Layer

Contains:

Source Port

Destination Port

SYN / ACK / FIN flags

Sequence and Ack numbers

You also captured:

TCP Retransmissions

TCP Keep-Alive packets

TCP Reset (RST)

HTTP 408 Request Timeout

HTTP 304 Not Modified

🔹 4. Application Layer (HTTP)


Saved Output:=

You exported the capture file as:

wireshark_capture.pcapng


How traffic was captured

Wireshark opened as Administrator

Selected Wi-Fi interface

Started live capture

Generated traffic by browsing websites

Applied filter tcp.port == 80 to view HTTP traffic


Findings

Multiple TCP packets

HTTP Request/Response

Server headers found

Timeout responses

Client & Server ports captured

Content-type: text/html


Conclusion

Wireshark successfully captured & analyzed network packets and identified HTTP flow between client and server.
