# Lab Report: Packet Crafting with Scapy

## Student and course details

- **Student name:** [Michael Adenyi]
- **Course:** [Cyber Security]
- **Instructor:** [Digital Eselsa]
- **Date performed:** [9/11/2026]
- **Operating system:** Kali Linux
- **Virtualization platform:** Oracle VirtualBox (if applicable)

## 1. Objectives

The objective of this practical exercise is to investigate Scapy, inspect protocol definitions, capture network traffic, create and send an ICMP packet, and create and send a TCP SYN packet in an authorized lab environment.

## 2. Tools and environment

- Kali Linux virtual machine
- Scapy
- Course-provided internal network, if available
- Terminal for generating test traffic

Record the actual interface and target used:

- **Interface:** [Record actual interface]
- **Authorized target:** [Record actual target]
- **Scapy version:** [Record version]

## 3. Procedure and observations

### Part 1 — Investigating Scapy

Commands used:

```python
ls()
ls(TFTP)
ls(IP)
```

**Observation:** [Describe the protocol information displayed in your VM.]

### Part 2 — Sniffing network traffic

Commands and traffic-generation steps used:

```python
sniff()
```

```bash
ping -c 5 www.cisco.com
```

After stopping the capture:

```python
a = _
a.summary()
```

**Observation:** [Describe the packets and protocols actually captured.]

### Part 3 — Creating and sending an ICMP packet

Course exercise command (only for the authorized course target):

```python
send(IP(dst="10.6.6.23")/ICMP()/"This is a test")
```

**Observation:** [Record Scapy's send result and what appeared in the capture.]

### Part 4 — Creating and sending a TCP SYN packet

Course exercise command (only for the authorized course target):

```python
send(IP(dst="10.6.6.23")/TCP(dport=445, flags="S"))
```

**Observation:** [Record the response flags and your interpretation. Do not claim a port state without observed evidence.]

## 4. Questions and answers

### What does the SA flag indicate in the packet returned from 10.6.6.23?

`SA` represents SYN-ACK. If this response is received for the tested port, it generally indicates that the port is open and listening because the host acknowledged the SYN request. Record the actual response observed in your capture.

### How can crafted TCP SYN packets be used to identify active ports?

A tester can send SYN probes to selected TCP ports on an authorized target and analyze the responses. A SYN-ACK generally indicates an open port, while a reset generally indicates a closed port. No response is inconclusive. This is technically **active reconnaissance**, rather than passive reconnaissance, because the tester transmits probes to the target.

## 5. Conclusion

[Summarize what you learned about Scapy, packet capture, ICMP packet construction, TCP SYN packets, and interpreting responses. Base the conclusion on your actual results.]

## 6. Evidence

Insert your genuine lab screenshots in the `screenshots/` folder and refer to them here:

1. Kali setup
2. Scapy version
3. Protocol inspection
4. Packet sniffing
5. ICMP packet
6. TCP SYN packet

Do not submit the supplied placeholder images as proof that the lab was completed.
