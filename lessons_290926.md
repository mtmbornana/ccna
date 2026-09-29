# NetworkChuck
## Routers, Hubs, Switches, IP Addresses, MAC Addresses, Wireles Access Points(WAPs)

### Routers

  - help networks talk to each other
  - A network is consisted of switches that are connected to a router and the router is connected to other routers?

### Hubs and Switches

<img width="289" height="215" alt="dumbhubs (2)" src="https://github.com/user-attachments/assets/66cdd5f6-fed5-4593-a0f8-ae924aa46b07" />
<br><br>

  - Hubs are dumb. As shown in the above image.
  - Switches are so much smarter.
      - Switches are layer 2 device.
      - It works with MAC addresses.
      - It can't see what goes on in layer 3 i.e. it doesn't see IP addresses.
  - All the messages that go throught the switches are referred to as frames.
  - Layer 2 = Switches & Frames

  <!-- IP Addresses in layer 3 are referred to as packets, but in real life frames are also often referred to as packets. -->

### Wireless Access Points(WAPs)
  
  - Basically do the same job as switches
  - But these are more like hubs than switches because they are just as dumb as hubs.  
            
---

# Labbing  

## Lesson 9

```
show startup-config
write memeory
show startup-config
```

- checking what is saved, saving running-config to startup-config, checking startup configuration

## Lesson 10

```
show running-config
show vlan
show interface status
```

- using show commands to audit the devices

```
interface g0/3
no shutdown
```
- bring the disabled port back online

```
end 
show running-config
write memeory
```

- return to previleged mode, verify, and save 

## Lesson 11

```
banner motd # Authorized Access Only #
```

- Setting a message-of-the-day banner
  - a warning banner for when someone connects.

```
show running-config

banner motd ^C
Authorized Access Only - Branch Office
^C
```
- You can verify the banner in the configuration.

## Lesson 12

```
enable password 'password'
```

- configures an unencrypted password for enable.

## Lesson 13

```
enable secret 'password'
```
- enable pasword saves the password as plain text in the running configuration file, making it readable to anyone with viewing access
- enable secret uses a strong, non-reversible cryptographic hash(such as MD5, SHA-256, or scrpt) by default

```
line console 0
password 'password'
login
```
- Configuring console line 0
  - a command to access the configuration mode for a network device's physical console port

## Lesson 14

- VTY lines (Virtual Teletype lines) are logical software interfaces on network consoles.
  - It lets administrators manage the device remotely using protocols like SSH(Secure Shell) or Telnet.

```
line vty 0 4
password 'password'
login
```
- This enables 5 simultaneous remote sessions of VTY lines & sets a password on the VTY lines.

## Lesson 15

```
username 'username' privilege 15 password 'password'

line vty 0 4
login local

exit
```
- This creates local user admin with previlege 15 & switches VTY lines to local username login

```
show running-config | section line vty

line vty 0 4
  transport input ssh
  login local
```
- With running-config, you can verify the configuration.

## Lesson 16

### Everything combined.

  ```
  enable ('password')
  configure terminal
  ```
  
- Entering global configuration mode with a password

  ```
  line console 0
  password 'password'
  login
  ```
  
- Securing console line

  ```
  line vty 0 4
  login local
  ```
  
- Securing VTY lines for remote access

  ```
  end
  show running-config
  write memory
  ```
- Verifying and saving the access configuration


## Exam 2 - SSH Into the Switch

```
hostname SW1
ip domain-name ccna.lab
```

- Setting the SSH identity (hostname + domain name)


```
username admin privilege 15 password 'password'
enable secret cisco
```

- Creating the admin account and enable secret


```
crypto key generate rsa modulus 2048
```

- Generating the RSA keys that SSH needs

```
interface vlan 1
ip address 192.168.1.1 255.255.255.0
no shutdown
```

- Giving the switch a management IP on VLAN 1

```
line vty 0 4
login local
transport input ssh
```

- Locking the VTY lines to SSH with local login

```
end
show running-config
write memory
```

- Verifying and saving the configuration

```
On the PC
ssh admin@192.168.1.1
```

- Connecting from the PC over SSH

---

Everything seems quite intuitive. <br>
This is just the very beginning. I'm sure it's going to get a lot more complex. <br>
I don't believe, however, that this exam is going to be as difficult as people say. <br>
I need to work harder and deeper. <br>
This isn't enough. 

  
