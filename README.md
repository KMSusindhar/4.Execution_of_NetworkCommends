# 4a.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## PROGRAM
## CLIENT:
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
## SERVER:
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
## OUTPUT
## PING COMMAND:
## CLIENT:
![324239291-c1bbcdee-8db7-4bb9-bd58-bb430be13862](https://github.com/KMSusindhar/4.Execution_of_NetworkCommends/assets/155904197/c8ccb3a8-6619-4521-9fd1-6572ef9e2615)



## SERVER:
![324239306-cec6c76d-a9ca-410a-aeb1-7ca9c02165d1](https://github.com/KMSusindhar/4.Execution_of_NetworkCommends/assets/155904197/750a5a04-01b2-4563-b326-9b7f7fe14cb0)



## TRACERT COMMAND:
![324239314-d6aba253-a9f1-4c1c-a4fd-c79928b1a4b4](https://github.com/KMSusindhar/4.Execution_of_NetworkCommends/assets/155904197/7c912c4b-a616-41e9-93ab-9c7bef7dd219)


## Result:
Thus Execution of Network commands Performed.
