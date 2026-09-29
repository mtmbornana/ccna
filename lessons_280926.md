# Lesson 1

```
- enable 
- ?
```
- global configuration
- configure terminal 


# Lesson 2

```
hostname name(branch-sw1)
end/exit
```
- Configuring hostname
- Moving back to EXEC mode

# Lesson 3


```
show running-config/show run 
```

- Verifying the configuration.
- Displaying current configuration active in the device's volatile RAM. Any changes you just made will appear here

```
do show running-config 
```

- While in config mode(configure terminal) the command "show running-config/show run" doesn't work. Putting "DO" command in front of it makes it work. 
- Each mode has its own command set, show lives in EXEC mode - from config mode you either exit back out or bring the command in with the 'do' prefix.

# Lesson 4

```
interface g0/1
```
- Entering interface configuration mode on g0/1


```
interface vlan 10 
```
- Entering vlan 10 configuration mode

# Lesson 5

```
en + tab
-> enable
```
- Tab completion

```
write(wr) memory
```
- Saving the configuration

```
sh st -> could mean anything -> sh startup-config
(now it's unique, it resolves to show startup-config)
```
- Abbreviation and its pitfalls 

```              
interface g0/1(int g0/1)
```
- Up arrow to recall the last command and modified it to g0/2

# Lesson 6

```
show vlan brief
```

- Showing which ports belong to which VLANs

```
configure terminal
int g0/1(the port of the vlan)
shutdown(no shutdown to turn it back on)
```

- Disabling and turning it back on with the "no"


# Lesson 7

```
vlan 10
vlan 20
```

- Creating vlan 10 and vlan 20

```
show vlan brief
```

- To see that vlan 10 and 20 appear

```
configure terminal
no vlan 10
no vlan 20
```

- To remove vlan 10 and 20

```
show vlan brief
```
- To see that vlan 10 and 20 don't appear
  
# Lesson 8

```
show interfaces status
```
- Shows the status of all interface

```
show ip interface brief
```
- Shows which interfaces are on
  
___

These lessons started with CISCO CLI. It was rather surprising because I thought it would naturally start with networking fundamentals. 
I was caught off guard, but it seems to be going well. I can follow through and did made exercises without looking at the solutions. 
I wouldn't be able to explain every single syntax if I were to be asked, but for now I understand the big picture. 
I am going to stick to this path and see what happens. 
