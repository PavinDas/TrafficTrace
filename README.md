
# TrafficTrace

<img src="https://socialify.git.ci/PavinDas/TrafficTrace/image?description=1&font=KoHo&language=1&name=1&owner=1&pattern=Solid&theme=Dark" alt="Socket" width="640" height="320" />


NetScanAnalyzer is a Python-based tool designed for network traffic analysis, intrusion detection, and log monitoring. It scans active hosts on a network, analyzes network logs, and detects suspicious activities like port scanning and large packet transfers that may indicate potential threats.



## Features

- **Network Scanning:** Identifies active hosts using ARP requests.

- **Log Analysis:** Parses network logs to identify frequent request sources and suspicious activities.

- **Traffic Visualization:** Displays top active IPs and protocol distributions using Matplotlib.

- **Anomaly Detection:** Detects port scanning and potential data exfiltration based on network traffic patterns.


## Installation

**Prerequisites**
Ensure you have Python installed (Python 3.7+ recommended). Install the required dependencies:

```bash
pip install scapy pandas matplotlib
```

    
## Usage

**1. Start the Server**
Run the server to listen for incoming network messages:
```bash
python3 server.py
```
**2. Send Messages from the Client**
Use the client script to send network messages:
```bash
python3 client.py
```
**3. Run Network Scanning & Log Analysis**
```bash 
sudo python3 main.py
```

## How It Works


**Network Scanning**
- Uses Scapy to send ARP requests and identify active hosts
- scans a given IP range (e.g., 192.168.1.1/24).

**Log Analysis**

- Parses network_logs.txt to count requests per IP.
- Identifies frequently occurring requests.

**Traffic Analysis**
- Reads network_traffic_logs.csv to visualize traffic trends.
- Detects potential port scanning (IPs targeting multiple destinations).
- Flags large packet transfers (possible data exfiltration attempts).


## Example

**Active Host Detection**
```
Scanning network for active hosts...
Active hosts:
IP: 192.168.1.10, MAC: AA:BB:CC:DD:EE:FF
IP: 192.168.1.12, MAC: FF:EE:DD:CC:BB:AA
```

**Suspicious Port Scanners**
```
Possible Port Scanners (IPs targeting multiple destinations):
192.168.2.50    19 destinations
```

**Large Packets Detected**
```
Large Packets Detected (Potential Data Exfiltration):
Timestamp            SourceIP      DestinationIP    PacketSize
2025-02-04 12:06:20  192.168.3.100 192.168.1.1    2000
```

## Contributing

Feel free to contribute by improving detection techniques or adding more features.
## License

This project is owned by [Pavin Das](https://github.com/PavinDas)


