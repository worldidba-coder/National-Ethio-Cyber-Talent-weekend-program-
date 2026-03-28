Week 3 Assignment
🧪 PCAP Analysis Challenges — Writeup
🛠 Tool Used
Wireshark
🧩 Challenge 1 — HTTP Analysis
Approach:
Applied filter:
http
Inspected HTTP requests (GET/POST)
Used Follow → HTTP Stream
Finding:
Discovered plaintext data in request/response
Extracted flag from visible content
🧩 Challenge 2 — DNS Analysis
Approach:
Applied filter:
dns
Used Follow → UDP Stream
Retrieved flag
🧩 Challenge 3 — TCP Stream Reconstruction
Approach:
Applied filter:
tcp
Used Follow → TCP Stream
Finding:
Data split across multiple packets
Reconstructed full message from stream
Extracted flag
🧩 Challenge 4 — Encoded TCP Payload
Approach:
Filtered packets with payload
Identified suspicious stream using:
Statistics → Conversations
Followed stream:
tcp.stream eq X
Finding:
Located encoded data in TCP stream
Decoded (Base64 )
Extracted flag
🧩 Challenge 5 — ICMP Covert Channel
Applied filter:
icmp && data
Finding:
Hidden data inside ICMP packets
Reconstructed message from multiple packets
Decoded if necessary
Extracted flag
🧠 Key Takeaways
HTTP → plaintext data leaks
DNS → data exfiltration via queries
TCP → streams reconstruct full conversations
Encoding → common obfuscation method
ICMP → covert channel for hidden data
