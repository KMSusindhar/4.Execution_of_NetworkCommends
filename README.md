# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command promt and Pycharm.

## Algorithms :

#### In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer
#### All commands related to Network configuration which includes how to switch to privilege mode
#### and normal mode and how to configure router interface and how to save this configuration to
#### flash memory or permanent memory.
#### This commands includes
#### • Configuring the Router commands
#### • General Commands to configure network
#### • Privileged Mode commands of a router
#### • Router Processes & Statistics
#### • IP Commands
#### • Other IP Commands e.g. show ip route etc.

## Program :
### Client :
```py
import socket
import requests

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)

while True:
    c, addr = s.accept()
    print("Connection from", addr)

    try:
        hostname = c.recv(1024).decode().strip()

        if hostname:
            try:
                response = requests.get("http://" + hostname)
                if response.status_code == 200:
                    c.send("Ping successful: Website is reachable".encode())
                else:
                    c.send("Ping failed: Website is not reachable".encode())
            except Exception as e:
                c.send("Ping failed: {}".format(e).encode())
        else:
            c.send("Hostname not provided".encode())
    except Exception as e:
        print("Error:", e)
    finally:
        c.close()
```
### Server :

```py
import socket
s = socket.socket()
s.connect(('localhost', 8000))
try:
    while True:
        ip = input("Enter the website you want to ping: ")
        s.send(ip.encode())
        response = s.recv(1024).decode()
        if response:
            print("Ping Result:", response)
        else:
            print("No response from server.")
except Exception as e:
    print("Error:", e)
finally:
    s.close()
```
### Trace Route :
```py
from scapy.all import *
target = ["www.google.com"]
result, unans = traceroute(target,maxttl=32)
print(result,unans)
```

## Output
### Client :
![Screenshot 2024-05-07 162424](https://github.com/KMSusindhar/4.Execution_of_NetworkCommends/assets/155904197/981df30d-0f19-40d0-ad2e-3988b7852c9d)

### Server :
![Screenshot 2024-05-07 162543](https://github.com/KMSusindhar/4.Execution_of_NetworkCommends/assets/155904197/a56e6136-e767-41c5-a686-5aad36c88db9)

### Trace command :
![Screenshot 2024-05-07 162609](https://github.com/KMSusindhar/4.Execution_of_NetworkCommends/assets/155904197/eb27c5ae-ff40-4140-a42a-4fa4696eb3ac)


## Result
Thus Execution of Network commands Performed 
