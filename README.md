if snort see two packets in a TCP flow with
• first packet has “login” or “Initial” in payload, destination port is 3399;
• and second packet has a “IPv4Address:Port”string(E.g. 123.45.6.7:8080) in payload. destination port is
3399;
• output a alert with msg “bot founded” and sid 1000001
