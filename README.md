Overview
TLScan3 is a Python-based scanner designed to enumerate encryption protocol support for specified targets. The script uses the argparse module to handle command-line arguments and provides detailed scanning and enumeration of supported TLS versions and their associated ciphers.

Features
Scans for supported TLS versions
Supports clear text protocol layers
Option to specify SNI (Server Name Indication)
Downgrade protection detection
Certificate retrieval for supported protocols
Requirements
Python 3.x
scanner module (containing TargetParser, Enumerator, start_tls)
TLS.protocols module (containing versions)
Usage
Basic Usage
To run the script, execute the following command:

sh
Copy code
python TLScan3.py <target>
Replace <target> with the target you want to scan, specified as host:port (e.g., www.example.com:443 or [::1]:443 for IPv6).

Options
--version: Display the script version.
<target>: Specify the target in the format host:port.
--sni <name>: Specify the SNI name to use in the handshake.
--<protocol>: Use a specified protocol layer (e.g., --smtp, --imap).
Examples
Scan a target with default settings:

sh
Copy code
python TLScan3.py www.example.com:443
Scan a target using a specific protocol layer:

sh
Copy code
python TLScan3.py www.example.com:443 --smtp
Scan a target with a specified SNI name:

sh
Copy code
python TLScan3.py www.example.com:443 --sni example.com
Error Handling
If the target parsing fails, the script will attempt to add a default port (443) and retry.
The script handles keyboard interrupts gracefully and will exit with a message if interrupted.
Verbose Mode
The enumerator runs in verbose mode by default, providing detailed output of the scanning process.
