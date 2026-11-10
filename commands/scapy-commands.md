# Scapy Lab Commands

Run these commands only in your authorized lab environment. Commands marked **course network** require the course-provided internal interface and target to exist.

## 1. Verify the Kali environment

In a Kali terminal:

```bash
whoami
ip -br addr
scapy --version
```

Install Scapy if it is missing:

```bash
sudo apt update
sudo apt install python3-scapy -y
```

## 2. Inspect Scapy protocols

Start Scapy:

```bash
sudo scapy
```

At the `>>>` Scapy prompt:

```python
ls()
ls(TFTP)
ls(IP)
```

Exit Scapy:

```python
exit()
```

## 3. Sniff general traffic

Terminal 1:

```bash
sudo scapy
```

At the Scapy prompt:

```python
sniff()
```

While the capture is running, use Terminal 2 to generate permitted traffic:

```bash
ping -c 5 www.cisco.com
```

Stop the capture with `Ctrl+C`. At the Scapy prompt, inspect the last returned packet list:

```python
a = _
a.summary()
```

## 4. Sniff ICMP on the course internal interface

First verify that `br-internal` appears in:

```bash
ip -br addr
```

Only if the course interface exists, use Scapy:

```python
sniff(iface="br-internal", filter="icmp", count=10)
```

In another terminal, and only if the authorized course target is present:

```bash
ping -c 10 10.6.6.23
```

After the capture finishes:

```python
a = _
a.nsummary()
```

## 5. Create and send an ICMP packet

For the course exercise, first start a capture on the authorized internal interface:

```python
sniff(iface="br-internal")
```

In a second terminal, launch Scapy:

```bash
sudo scapy
```

Send the exercise packet only to the authorized course target:

```python
send(IP(dst="10.6.6.23")/ICMP()/"This is a test")
```

Stop the capture in Terminal 1 with `Ctrl+C`, then inspect it:

```python
a = _
a.nsummary()
```

## 6. Create and send a TCP SYN packet

Use only the designated course target. Start a capture on the course interface:

```python
sniff(iface="br-internal")
```

In a second Scapy terminal:

```python
send(IP(dst="10.6.6.23")/TCP(dport=445, flags="S"))
```

Stop the capture and inspect the returned packets:

```python
a = _
a.nsummary()
```

### Interpreting the response

- `SA` means SYN-ACK and generally indicates that the port is open.
- `RA` or a reset response generally indicates that the port is closed.
- No response is inconclusive; filtering, packet loss, or routing may be involved.

**Terminology note:** Sending SYN probes is active reconnaissance, not passive reconnaissance, because packets are deliberately transmitted to the target.

## Important troubleshooting

If `br-internal` is not listed by `ip -br addr`, do not run the course-interface commands unchanged. Your VM may not be connected to the course's internal network. Configure the lab network according to your instructor's VirtualBox instructions, or ask the instructor for the correct interface and target. Do not substitute an unrelated host.
