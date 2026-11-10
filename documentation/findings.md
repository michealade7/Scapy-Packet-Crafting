# Lab Findings

Record only observations verified in your own Kali VM. Replace the prompts below with your actual output and results.

## 1. Scapy and protocol inspection

- Scapy version:
- Result of `ls()`:
- Number of TFTP fields reported by `ls(TFTP)`:
- Notable IPv4 fields reported by `ls(IP)`:

## 2. Packet sniffing

- Interface used:
- Capture filter:
- Packet count:
- Protocols observed:
- Result of `a.summary()` or `a.nsummary()`:

## 3. ICMP packet

- Destination used (authorized lab host):
- Command used:
- Scapy send result:
- Packets observed in the capture:
- Interpretation:

## 4. TCP SYN packet

- Destination used (authorized lab host):
- Destination port tested:
- Command used:
- Response flags observed:
- Interpretation:

## 5. Limitations and notes

- Was the course interface `br-internal` present?
- Was the course target reachable?
- Any errors or unexpected results:
- How the issue was resolved:

> A SYN-ACK (`SA`) response generally indicates that the tested TCP port is open and listening. A reset response generally indicates a closed port. No response is inconclusive and may result from filtering, packet loss, or routing issues.
