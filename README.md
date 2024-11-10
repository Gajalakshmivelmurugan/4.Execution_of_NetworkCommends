# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
All commands related to Network configuration which includes how to switch to privilege mode
and normal mode and how to configure router interface and how to save this configuration to
flash memory or permanent memory.
This commands includes
• Configuring the Router commands
• General Commands to configure network
• Privileged Mode commands of a router
• Router Processes & Statistics
• IP Commands
• Other IP Commands e.g. show ip route etc.

## Program

Ping Command
```
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
 ```       
server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
 ```   
Traceroute Command
```
from scapy.all import*
target = ["www.google.com"]
result, unans = traceroute(target,maxttl=32)
print(result,unans)
```
## Output
client

![382574609-be7ffff6-e081-4307-b8ad-dda657006980](https://github.com/user-attachments/assets/90b405b7-9e60-4bfd-8c71-40bc0daf015d)

server

![382574626-0b27d319-ac21-4137-9ba4-e24baa545653](https://github.com/user-attachments/assets/54e3f066-6ece-494d-a0ec-712fb99a95d4)

Traceroute Command

![382574652-5320d5d1-6377-40ac-bd2a-3b3ff2eb5d64](https://github.com/user-attachments/assets/21c3c349-4461-4f8e-94f5-ffd499420a1b)

## Result
Thus Execution of Network commands Performed 
