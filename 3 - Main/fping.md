Tags: [[Hacking]] [[Port Scanning]] [[Enumeration]]

--- 
# Using range
## Usage
```
fping -g 192.168.0.0/24
```

## Output
```
192.168.0.1 is alive
192.168.0.2 is unreachable
```

# Using list
## Usage
```
fping -t ip_list.txt
```

> [!tip] list must be one IP per line

## Output
```
192.168.0.1 is alive
192.168.0.2 is unreachable
```
