Date: 14-10-2024 08:28

Tags: [[Hacking]]

---

# With NMAP
`nmap -sV --script=banner scanme.nmap.org`

# With cURL
`curl -s -I scanme.org | grep -e "Server: "`

# With TELNET
`telnet scanme.org 22`

# With netcat
`nc -v scanme.org 22

# With dmtry
`dmitry -b scanme.org`