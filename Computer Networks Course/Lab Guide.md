# Lab Guide - Computers Network Course

**How to search information about the network devices**
 1. Go to <support.huawei.com>
 2. Click on the **Enterprise** button
 3. You can look for the device you are looking information for below where it says **"Enterprise Network"**.
 4. Once you have entered to a device, select the model of the device you are looking for
 5. Scroll down and you will see a tab called **"Documentation"**, click on it and from there you can search for the product documentation.
 6. Opening the *hdx* shows the documentation of the product. You can look the product where it says *"Chasis"* or the configuration on *"Configuration" > "CLI-based Configuration"*.
 
> 💡 The software where the labs are done is called "eNSP".
 
## Basic Operation of Huawei 
 > 💡  This lab configures Huawei devices to learn about and get familiar with the basic operations of Huawei VRP
 
### Topology
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/b1097404-f664-467d-b36a-4b8ae7a24512)


In order to finish this lab, follow the next steps:
### Step 1: Start the device
 1. Drag a *"Router"* to the board
 2. Start the device: Right-click on the Router > Start device.
 
### Step 2: View Basic Device Information
 1. In order to access to the CLI of the router: Right-click on the Router > CLI. This is where all configuration is done.
 2. In order to see the device version information:
	 ```
	 <Huawei>display version
	 ```

### Step 3: Complete basic device configuration	
 
 1. Change the name of the router, entering to the **System view** to *"R1"*:
	```
	<Huawei>system-view
	[Huawei]sysname R1
	```
 2. Enter to the **Interface view **(Where we modify the ports of the router) and add an IP address:
	```
	[R1]interface g
	[R1]interface GigabitEthernet0/0/0
	[R1-GigabitEthernet0/0/0]
	[R1-GigabitEthernet0/0/0] ip address 192.168.1.1 24
	```
	If you need to exit from an interface, type `quit` or `q` to a lower-level view.
 3. To get help from the system to remember a command:
	```
	[R1]i?
	icmp
	igmp-snooping
	info-center
	ip
	ipv6
	[...]
	```
 4. To get help from the system to remember all the options from a command:
	```
	[R1-GigabitEthernet0/0/0] ip ?
	address    Address
	apply      Apply security policy
	binding    Enable binding of an interface with a VPN instance
	[...]
	[R1-GigabitEthernet0/0/0] ip address ?
	X.X.X.X     IP address
	bootp-alloc IP address allocated by BOOTP
	[...]
	```
5. Let's just set an IP address manually:
	```
	[R1-GigabitEthernet0/0/0] ip address 10.0.0.1 24
	```
6. If you need to display the running configuration in the current view, insert:
	```
	[R1-GigabitEthernet0/0/0] display this
	[...]
	[R1-GigabitEthernet0/0/0] display current-configuration
	[...]
	``` 
	Let's remember that the devices support incomplete keyword input, for example, `dis cu` is equivalent `display current-configuration`. Finally, with *tab* you can auto-complete the commands if it's possible.
7. Now we need to delete the IP address configuration of GigabitEthernet 0/0/0. This can be possible using the undo command:
	```
	[R1]interface GigabitEthernet 0/0/0
	[R1-GigabitEthernet0/0/0] undo ip address
	```
	And if you display the information again with `display this`, it will be empty.

### Step 4: Save the current device configuration
1. In order to save the current device configuration:
	```
	<R1>save
	```
	> 💡 The save command saves the configuration to the default path and overwrite the original configuration file. 
	You can also run it to save the current configuration to a specified file on the storage device.
2. You can also compare the current configuration with the configuration used for the next startup:
	```
	<R1> compare configuration
	```

### Step 5: Operating the File System of the Device
1. You can display the file list in the current directory:
	```
	<R1> dir
	```
	> 💡 **vrpcfg.zip:** Configuration file. Must be *.cgf* or *.zip* extension.
	**ar651c-v300r019c00Sspc100.cc:** System software. Must be a.cc extension.
2. Let's now save the current configuration but in another file:
	```
	<R1>save test.cfg
	```
	If you use the `dir` command again, you will see the *test.cfg* file there.
3. Now with that file, you can set it to the configuration file used for the next startup
	```
	<R1>startup saved-configuration test.cfg
	```
4. And if you need to display the file used for the next startup:
	```
	<R1>display startup
	```
	> 💡 This commands displays the system software, backup system software, configuration file, license file, patch file, and voice file related to the current and next startup of the device.
5. Finally, let's clear the configuration file:
	```
	<R1>reset saved-configuration
	```
### Step 6: Restart the device
1. Let's restart the device:
	```
	<R1>reboot
	```

### Questions and Additional Contents
- ¿In step 5, the reset saved-configuration command is used to clear the configuration. Why is the configuration still retained after the switch is restarted?
	**Answer:** Because we set up the configuration file for the next startup in the same step.

### Appendix
|     **Function Keys**    |                             ** Function**                            |
|:------------------------:|:--------------------------------------------------------------------:|
| <Ctrl+A>                 | Moves the cursor to the beginning of the current line                |
| <Ctrl+B>                 | Moves the cursor one character to the left                           |
| <Ctrl+C>                 | Stop the currently executing function                                |
| <Ctrl+D>                 | Deletes the character at the current cursor position                 |
| <Ctrl+E>                 | Move the cursor to the end of the last line                          |
| <Ctrl+F>                 | Moves the cursor one character to the right                          |
| <Ctrl+H>                 | Deletes one character to the left of the cursor                      |
| <Ctrl+K>                 | Terminate outgoing connections during connection establishment phase |
| <Ctrl+N> or "Cusor"      | Displays the next command in the history command buffer.             |
| <Ctrl+P> or arrow cursor | Displays the previous command in the history command buffer.         |
| <Ctrl+T>                 | Enter the question mark "?"                                          |
| <Ctrl+W>                 | Deletes a string (word) to the left of the cursor                    |
| <Ctrl+X>                 | Deletes all characters to the left of the cursor                     |
| <Ctrl+Y>                 | Deletes the cursor position and all characters to its right.         |
| <Ctrl+Z>                 | Return to User View                                                  |
| <Ctrl+]>                 | Terminating an Incoming Connection or Redirect Connection.           |
| <Esc+B>                  | Moves the cursor one string (word) to the left.                      |

## VLAN Technology Experiment
 > 💡 This lab describes how to configure Huawei switches to learn about VLAN configurations.
> **Note from the author:** The teacher explaining the guide makes the connections on different ports, but the process is the same. Here I explain the proccess from the Guide Lab
 
### Topology
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/e0b43356-1a74-497a-a3aa-a4e1053ea979)

In order to finish this lab, follow the next steps:
### Step 1: Start the devices
1. Build the topology:
	
 https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/7808ff30-418e-4391-bdeb-513efd1eacd3
 
2. Start the devices. If the points are all green means that all the devies have started.

### Step 2: Configure S1 and S2 device names
1. Open the Command Line Interface (CLI) of LSW1 and insert the next route of commands:
	```
	<Huawei> system-view
 	[Huawei] sysname S1
	```
2. Repeat the process for LSW2

### Step 3: Configure Host IP Addresses
1. Configure the IP addresses for PC1 (Double-click on the PC) and apply the changes:

https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/57ee0a27-196e-44d7-9696-441567dd4e8a

	> 💡 The subnet mask on the table is 24, which is translated to the Subnet Mask to 255.255.255.0. If it were 25, it would be 255.255.255.128 because remember that the subnet mask works in binary.
 	> Also, because they are in the same subnet, we do not need to set the gateway.

2. Repeat the process for the rest of PCs. Use the table that is referred in the guide.

### Step 4: Creating VLANs
1. Create VLANs 2 and 3 on S1:
	```
	[S1] vlan batch 2 to 3
 	```
 	What we are indicating here is to create vlans from number two to number three. So if we only needed one vlan, the command would be `vlan batch 2`

2. Repeat the same command on S2

### Step 5: Configuring Interface-based VLAN Classification
Basically, we need to configure every interfaces of the switches and set the default vlan of where the port is going to be

**On S1**

1. Go to the `g0/0/01` interface in order to configure the interfaces connecting S1 and S2 as **access** interfaces:
	```
 	[S1] int g0/0/01
 	```
2. Configure it as an access type interface:
	```
 	[S1-GigabitEthernet0/0/1] port link-type access
	```
 	> 💡 **Access ports (`access`):**
  	> - Belong to one VLAN.
	> - Commonly used to connect computer ports.
	> **Trunk ports (`trunk`):**
	> - Allow multiple VLANs through.
	> - Receive and send multiple VLAN packets.
	> - Typically used for connection between switches.
	> **Hybrid ports (`hybrid`):**
	> - Allow multiple VLANs through
	> - Receive and send multiple VLAN packets
	> - Used for connection between switches, or switch and computer
	> This website explains it in a good way! https://www.utepo.net/article/detail/Access-Port-vs-Trunk-Port-vs-Hybrid-Port.html

3. And now let's set the default VLAN of that port:
	```
 	[S1-GigabitEthernet0/0/1] port default vlan 2
	```
4. Let's do the same steps but for the `g0/0/2` interface:
	```
 	[S1] interface GigabitEthernet0/0/2
	[S1-GigabitEthernet0/0/2] port link-type access
	[S1-GigabitEthernet0/0/2] port default vlan 3
 	```
	> 💡 Remember that with `q`you can quit from an interface

5. And finally for the `g0/0/10` interface, configure it as a trunk interface and allow only VLANs 2 and 3 to pass through:
	```
 	[S1] interface GigabitEthernet0/0/10
	[S1-GigabitEthernet0/0/10] port link-type trunk
	[S1-GigabitEthernet0/0/10] port trunk allow-pass vlan 2 3
 	```

6. Because of security reasons, the VLAN 1 is in the allowed list by default. **If it has no actual service usage, you nee to delete it for security purposes**:
	```
 	[S1-GigabitEthernet0/0/10]undo port trunk allow-pass vlan 1
 	```
	> 💡 The `undo port trunk allow-pass vlan` command deletes the VLAN to which a trunk interface is added

**ON S2**
Repeat the same steps:
```
[S2] int g0/0/14
[S2-GigabitEthernet0/0/14] port link-type access
[S2-GigabitEthernet0/0/14] port default vlan 3
[S2-GigabitEthernet0/0/14] q
[S2] int g0/0/2
[S2-GigabitEthernet0/0/2] port link-type access
[S2-GigabitEthernet0/0/2] port default vlan 2
[S2-GigabitEthernet0/0/2] q
[S2] int g0/0/10
[S2-GigabitEthernet0/0/10] port link-type trunk
[S2-GigabitEthernet0/0/10] port trunk allow-pass vlan 2 3
```

### Step 6. Viewing Configuration Information
You can display the VLAN information on a switch with:
```
[S1] display vlan
```

The output should look like this:
```
The total number of vlans is: 4
---------------------------------------------------------------------------------------------------------------------
U: Up; D: Down; TG: Tagged; UT: Untagged;
MP: Vlan-mapping; ST: Vlan-stacking;
#: ProtocolTransparent-vlan; *: Management-vlan;
---------------------------------------------------------------------------------------------------------------------
VID Type Ports
----------------------------------------------------------------------------------------------------------------------
1 common UT:GE0/0/2(D) GE0/0/3(D) GE0/0/4(D) GE0/0/5(D)
GE0/0/6(D) GE0/0/7(D) GE0/0/8(D) GE0/0/9(D)
GE0/0/11(D) GE0/0/12(D) GE0/0/14(D) GE0/0/15(D)
GE0/0/16(D) GE0/0/17(D) GE0/0/18(D) GE0/0/19(D)
GE0/0/20(D) GE0/0/21(D) GE0/0/22(D) GE0/0/23(D)
GE0/0/24(D)
2 common UT:GE0/0/1(U)
TG:GE0/0/10(U)
3 common UT:GE0/0/2(U)
TG:GE0/0/10(U)
VID Status Property MAC-LRN Statistics Description
------------------------------------------------------------------------------------------------------------------------
1 enable default enable disable VLAN 0001
2 enable default enable disable VLAN 0002
3 enable default enable disable VLAN 000
```
As you can see, where it says `"2 common"` and `"3 common"`, there you can see that the access interfaces and the trunk interfaces are working correctly

### Result verification
It's only neccesary to check the connectivity of the devices and verify the VLAN configuration. You can follow the steps easily:
1. Run the ping command on PC1 to verify that PC1 can ping PC4
	```
 	PC> ping 10.1.3.4
 	```
 	and the output should say that there is not packet loss
2. Run the ping command again on PC1 to verify if PC1 can ping PC2
	```
 	PC> ping 10.1.3.2
 	```
 	and the output should say that there is packet loss

### Configuration files

#### Configuration of S1
```
sysname S1
#
vlan batch 2 to 3
#
interface GigabitEthernet0/0/1
port link-type access
port default vlan 2
#
interface GigabitEthernet0/0/2
port link-type access
port default vlan 3
#
interface GigabitEthernet0/0/10
port link-type trunk
undo port trunk allow-pass vlan 1
port trunk allow-pass vlan 2 to 3
#
```

#### Configuration of S2
```
sysname S2
#
vlan batch 2 to 3
#
interface GigabitEthernet0/0/1
port link-type access
port default vlan 2
#
interface GigabitEthernet0/0/10
port link-type trunk
undo port trunk allow-pass vlan 1
port trunk allow-pass vlan 2 to 3
#
interface GigabitEthernet0/0/14
port link-type access
port default vlan 3
#
```



