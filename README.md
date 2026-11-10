# Scapy Packet Crafting Lab

A structured, hands-on cybersecurity lab documenting packet inspection and packet crafting with **Scapy** in an authorized Kali Linux virtual-machine environment.

## Lab objectives

1. Investigate Scapy and inspect protocol definitions.
2. Sniff and summarize network traffic.
3. Create and send an ICMP packet.
4. Create and send a TCP SYN packet and interpret the response.

## Lab environment

- **Operating system:** Kali Linux
- **Virtualization:** Oracle VirtualBox (if used for your lab)
- **Tool:** Scapy
- **Course lab interface:** `br-internal` (only when it exists in the supplied lab environment)
- **Course lab target:** `10.6.6.23` (only when this host is provided and reachable in the authorized lab)

> **Safety:** Perform packet crafting and probing only on systems and networks you own or have explicit permission to test. Do not assume that `br-internal` or `10.6.6.23` exists on a standard Kali installation. Verify the lab interface and target before sending traffic.

## Repository structure

```text
Scapy-Packet-Crafting-Lab/
├── README.md
├── documentation/
│   ├── introduction.md
│   ├── ipv4-header.md
│   └── findings.md
├── commands/
│   └── scapy-commands.md
├── screenshots/
│   ├── 01-kali-setup.png
│   ├── 02-scapy-version.png
│   ├── 03-protocols.png
│   ├── 04-packet-sniffing.png
│   ├── 05-icmp-packet.png
│   └── 06-tcp-syn.png
└── report/
    └── lab-report.md
```

## Getting started

1. Start the authorized Kali lab VM.
2. Check your account and network interfaces:

   ```bash
   whoami
   ip -br addr
   ```

3. Check whether Scapy is installed:

   ```bash
   scapy --version
   ```

4. If it is not installed, install the Kali package:

   ```bash
   sudo apt update
   sudo apt install python3-scapy -y
   ```

5. Follow [`commands/scapy-commands.md`](commands/scapy-commands.md) and record your actual observations in [`documentation/findings.md`](documentation/findings.md) and [`report/lab-report.md`](report/lab-report.md).

## Evidence

The six PNG files in `screenshots/` are clearly marked placeholders. Replace each with your own genuine screenshot from the lab before presenting this repository as completed evidence.

## Learning reference

- [Scapy official documentation](https://scapy.readthedocs.io/en/latest/introduction.html)

## Author

Add your preferred name, course, instructor, and completion date to the lab report before submission.
