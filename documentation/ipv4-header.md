# IPv4 Header Fields in Scapy

Use the following command in the Scapy interactive prompt:

```python
ls(IP)
```

The lab asks you to inspect the IPv4 fields. Common fields shown by Scapy include:

| Field | Meaning |
|---|---|
| `version` | IP version number; IPv4 uses 4 |
| `ihl` | Internet Header Length |
| `tos` | Type of Service / differentiated services field |
| `len` | Total length of the IP packet |
| `id` | Identification value used in fragmentation |
| `flags` | Fragmentation-related flags |
| `frag` | Fragment offset |
| `ttl` | Time To Live |
| `proto` | Encapsulated protocol number |
| `chksum` | Header checksum |
| `src` | Source IPv4 address |
| `dst` | Destination IPv4 address |

The exact display and defaults depend on the installed Scapy version. Use the output from your own VM as the primary evidence for the lab.
