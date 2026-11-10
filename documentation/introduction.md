# Introduction to Scapy

## What is Scapy?

Scapy is a Python-based interactive packet manipulation tool. It can create, dissect, send, receive, and inspect network packets. It is useful for learning how network protocols are structured and for conducting authorized network troubleshooting and security testing.

## Lab purpose

This lab introduces the Scapy interactive environment and uses it to:

- inspect protocol definitions;
- capture and summarize network packets;
- construct and send an ICMP packet;
- construct and send a TCP SYN packet; and
- interpret packet responses.

## Environment and authorization

Use the course-provided Kali Linux environment and its designated internal network. Before using a course-specific interface or target, verify that it exists in the VM. The worksheet refers to interface `br-internal` and target `10.6.6.23`; these are not guaranteed to exist in a separately configured VirtualBox installation.

Only capture or transmit traffic on networks and hosts for which you have permission.

## Starting Scapy

```bash
sudo scapy
```

Alternatively, enter a root shell and launch Scapy:

```bash
sudo su
scapy
```

At the Scapy prompt, `ls()` lists available protocol layers. `ls(TFTP)` and `ls(IP)` display the fields associated with those protocol definitions.
