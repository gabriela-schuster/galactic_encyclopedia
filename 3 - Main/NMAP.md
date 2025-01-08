Date: 26-09-2024 08:18

Tags: [[Hacking]] [[Port Scanning]] [[Enumeration]]

---

## Scanning ports

> [!summary] Pro tip: use `scanme.nmap.org` to test your nmap scans

### The basic
Will run on predefined 100 default ports
`nmap -sS 192.168.0.1`

- -A: gets OS and versions
- -F: a Fast scan
- -f: fragment protocol headers
- -T0: timing, 0 is slower, 5 is faster

- -sS: syn scan
- -sT: TCP scan
- -sU: UDP scan
- -sF: FYN scan
- -sA: ACK scan
- -sX: XMAS scan
- -sN: null scan
- -sP: ping scan
- -sO: protocol scan
- -sW: windows scan
- -sR: RPC scan
- -sL: list scan
- -sl: idle scan
- -sV: service versions

- -Po: don't ping, no ICMP protocol
- -PT: TCP ping
- -PS: SYN ping
- -Pn: treat hosts as online, no ICMP protocol send

many many MANY more...

use https://explainshell.com/ for an explanation of a given shell command

## NMAP script engine
> [!sumary] If using Kali Linux, `/usr/share/nmap/scripts` has all the scripts currently available

### Using scripts
`namp --script=http-enum scanme.org`
where `http-enum` is the name of the script

## bypassing firewalls
### Using decoys
uses the 192.168.0.10,192.168.0.11,192.168.0.12 IPs as decoys
`nmap -D 192.168.0.10,192.168.0.11,192.168.0.12 scanme.org`

#### Random decoys
`nmap -D Rnd:10 scanme.org`

### Spoofing
`nmap -e eth0 -S 192.168.0.18 scanme.org`
makes it seems as 192.168.0.18 is the one attacking

> [!sumary] `--e` specifies the network device which will spoof of

`nmap -e eth0 -S 192.168.0.18 --spoof-mac Dell scanme.org`
to spoof MAC address too

> [!sumary] `--spoof-mac 0` randomizes the MAC

### Half open scan (ACK scan)
`nmap -sA scanme.org`

### Package fragmentation
spreads the IP protocol header into many parts, makes it hard to detect from a firewall perspective
`nmap -sT -f scanme.org`

### Delay
There are some firewalls protections that blocks if we try to scan a vast number of ports at a given time, a delay may help in those cases
`nmap -sS --scan-delay 5s scanme.org`

### Send random data
`nmap --data-length 1200 scanme.org`
sends some data to confuse any defense mechanism

### Bad checksum
Sends a bad checksum, makes it seems the package sent is invalid, and doesn't poses any risk
`nmap --badsum scanme.org`