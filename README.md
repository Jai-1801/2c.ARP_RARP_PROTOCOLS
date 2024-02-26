# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP

## CLIENT
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
 ip=c.recv(1024).decode()
 try:
 c.send(address[ip].encode())
 except KeyError:
 c.send("Not Found".encode())
```
## SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
REG NO:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode()
```

## OUTPUT - ARP

## CLIENT
![307534334-d31ec479-a0fa-456c-9af0-9794aa9e4790](https://github.com/Jai-1801/2c.ARP_RARP_PROTOCOLS/assets/139335300/1784468c-1983-4750-ae4b-ba278089a79e)

## SERVER
![307534584-535fe830-b3e7-4b51-8357-dacd111e6a89](https://github.com/Jai-1801/2c.ARP_RARP_PROTOCOLS/assets/139335300/af00dd9b-4c4c-47a7-b19e-5510882d1ca6)

## ALGORITHM - RARP

## CLIENT
```
1.Start the program

2.Using datagram sockets UDP function is established.

3.Get the MAC address to be converted into IP address.

4.Send this MAC address to server.

5.Server returns the IP address to client.
```
## SERVER
```
1.Start the program.

2.Server maintains the table in which IP and corresponding MAC addresses are stored.

3.Read the MAC address which is send by the client.

4.Map the IP address with its MAC address and return the IP address to client.
```
## PROGRAM - RARP

## CLIENT
```
import socket 
s=socket.socket() 
s.bind(('localhost',9000)) 
s.listen(5) 
c,addr=s.accept() 
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"}; 
while True: 
            ip=c.recv(1024).decode() 
            try: 
                c.send(address[ip].encode()) 
            except KeyError: 
                c.send("Not Found".encode())
```
## SERVER
```
import socket 
s=socket.socket() 
s.connect(('localhost',9000)) 
while True: 
    ip=input("Enter MAC Address : ") 
    s.send(ip.encode()) 
    print("Logical Address",s.recv(1024).decode())
```
## OUTPUT -RARP

## CLIENT
![307534638-0e28f4ca-b4ce-4c03-82e8-925588037283](https://github.com/Jai-1801/2c.ARP_RARP_PROTOCOLS/assets/139335300/8393b5c1-f5af-4dea-987b-26c4f70cbb05)

## SERVER
![307534776-12abb479-b059-42cc-bfc8-2b2f31f30175](https://github.com/Jai-1801/2c.ARP_RARP_PROTOCOLS/assets/139335300/27518029-ec77-484f-89c1-2f1bb38849ae)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
