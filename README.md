# Port Scanner

A Basic port scanner to use on Linux.

## Key Features & Benefits

*   **Basic Port Scanning:** Scans specified ports on a given IP address.
*   **Scan Types:** Supports SYN ACK, UDP, and Comprehensive scan types.
*   **Nmap Integration:** Leverages the `nmap` library for port scanning capabilities.
*   **Simple Automation:** Provides a command-line interface for easy automation.

## Prerequisites & Dependencies

*   **Python 3.x:** Ensure Python 3 is installed on your Linux system.
*   **Nmap:** Requires Nmap to be installed.
    ```bash
    sudo apt update
    sudo apt install nmap
    ```
*   **Python Nmap Library:** Install the `python-nmap` library.
    ```bash
    pip install python-nmap
    ```

## Installation & Setup Instructions

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/Paddywelch117/PortScanner.git
    cd PortScanner
    ```

2.  **Install Dependencies:**
    ```bash
    pip install python-nmap
    ```

## Usage Examples & API Documentation

### Running the Scanner

1.  **Execute the Script:**
    ```bash
    python Scanner.py
    ```

2.  **Follow the Prompts:**
    *   Enter the IP address to scan.
    *   Select the type of scan to perform (SYN ACK, UDP, or Comprehensive).

### Example Usage

```python
import nmap

scanner = nmap.PortScanner()

ip_addr = "127.0.0.1" # Replace with desired IP address
scan_type = 1 # 1: SYN ACK, 2: UDP, 3: Comprehensive

if scan_type == 1:
    scanner.scan(ip_addr, arguments="-sS") # SYN ACK Scan
elif scan_type == 2:
    scanner.scan(ip_addr, arguments="-sU") # UDP Scan
elif scan_type == 3:
    scanner.scan(ip_addr, arguments="-sS -sV -sC -A -O") # Comprehensive Scan

print(scanner.scaninfo())
print(scanner[ip_addr].tcp().keys())
```

## Configuration Options

No specific configuration file is required. You can modify the `Scanner.py` script directly to customize scan arguments or add more scan types.

## Contributing Guidelines

Contributions are welcome! Please follow these guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Make your changes.
4.  Submit a pull request with a clear description of your changes.

## License Information

No license specified. All rights reserved.

## Acknowledgments

*   [Nmap](https://nmap.org/) - The powerful port scanner used by this script.
*   [python-nmap](https://pypi.org/project/python-nmap/) - Python library for interacting with Nmap.
