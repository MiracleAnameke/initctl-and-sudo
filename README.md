# initctl and sudo

## Lab Overview

This lab focuses on utilizing initctl for controlling services and understanding the sudo command in a Linux environment. Students will configure network settings, manage services with initctl, and use sudo for executing commands with elevated privileges.

## Preparation

- Use VMs from previous labs: Server 2008R2, Windows 7/10, and Ubuntu.
- Set up a LAN segment called INFO6003 and configure IPs for each VM.

## Lab Tasks and Screenshots

### Slide 1: Using initctl to Restart Network Interface

- **Task**: Configure the Ubuntu VM's network settings and use initctl to restart the network interface. Determine which service to restart and address any command failures.
- **Screenshot for Slide 1**: Show the interface successfully restarting, including any errors and the final successful command, along with `uname -a` output.
  <img src="https://i.imgur.com/PagOlcA.png" height="400px" width="auto" alt="initctl Network Interface Restart"/>

### Slide 2: Confirming Network Connectivity

- **Task**: Confirm connectivity to your Windows VMs from the Ubuntu VM using ping commands. Utilize grep to filter the output to show lines including ttl.
- **Screenshot for Slide 2**: Clear the screen with the clear command then show the output of two pings filtered to just show lines including ttl, followed by `uname -a` command.
  <img src="https://i.imgur.com/BrMV0AW.png" height="400px" width="auto" alt="Network Connectivity Confirmation"/>

### Slide 3: Network Configuration on Windows VM

- **Task**: Log into the Windows 7 VM as the domain administrator and gather information about the network configuration, focusing on the LAN Segment setting and name filtering with `net config workstation`.
- **Screenshot for Slide 3**: Show the `net config workstation` output filtered to lines with name and LAN Segment Setting for the Windows VM.
  <img src="https://i.imgur.com/VjYYKW2.png" height="400px" width="auto" alt="Windows VM Network Configuration"/>

### Slide 4: Demonstrating Sudo with tcpdump

- **Task**: Demonstrate the sudo command by granting limited user permission to execute tcpdump, capture network traffic, and then view the output. Address any permission errors and edit the sudoers file as needed.
- **Screenshot for Slide 4**: Include the tcpdump output capturing at least one request and reply and the output of the `uname -a` command.
  <img src="https://i.imgur.com/vP1EcTi.png" height="400px" width="auto" alt="Sudo with tcpdump"/>

## Lab Questions and Answers

1. **Which service was restarted using initctl?** 
   - The network-interface service was targeted for restart.
2. **Why did the command fail initially?** 
   - The command failed because it wasn’t run as a superuser. Root privileges are necessary for service management commands.
3. **What does the '-n' flag not do in the ping command?** 
   - The '-n' flag doesn’t convert addresses; it's often used to show numeric addresses instead of hostnames.
4. **Why didn't the sudo command succeed with user manameke-02?** 
   - It should not succeed because manameke-02 lacks the necessary rights. The error indicates that the command is not being executed by a user account with the necessary su rights.


