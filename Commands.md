# Introduction
This file contains a collection of Command Prompt (MS-DOS) commands that I have found to be useful. I have gathered these commands in one place as a reference point to refer back to whenever I need them.

<details>
<summary><b><font size="+1">System</font></b></summary>
</br>

Checks the primary disk and attempts to repair any problems.

``chkdsk /f``

Scans protected system files and replaces incorrect versions with Microsoft versions.

``sfc /scannow``

Checks the health of the Windows operating system image and reports any issues it finds, but it does not fix them.

``DISM /Online /Cleanup-Image /CheckHealth``

Checks the health of the Windows operating system image and reports any issues it finds. It also attempts to fix any issues it finds.

``DISM /Online /Cleanup-Image /ScanHealth``

Checks the health of the Windows operating system image and attempts to fix any issues it finds using Windows Update. If Windows Update is unable to fix the issues, the /RestoreHealth option will use the component store to try to repair the image.

``DISM /Online /Cleanup-Image /RestoreHealth``

Immediately restarts the computer into firmware setup. All programs will be closed without warning.

``shutdown /r /fw /f /t 0``

Creates a new background service.

```
sc.exe Create "<service name>" 
binPath="<file path>" 
DisplayName="<service display name>"
```

Displays the version information of the .NET Framework.

``reg query "HKLM\SOFTWARE\Microsoft\Net Framework Setup\NDP" /s``
</details>

<details>
<summary><b><font size="+1">Processes</font></b></summary>
</br>

Displays all running processes that match the string.

``tasklist | findstr "<string>"``

Forces the process with the supplied PID to terminate.

``taskkill /f /pid <PID>``
</details>

<details>
<summary><b><font size="+1">Network</font></b></summary>
</br>

Pings a host by sending an ICMP echo request and waiting for an ICMP echo reply.

``ping <host>``

Pings a host continuously until stopped.

``ping <host> /t``

Displays current TCP/IP connections.

``netstat -ano -p tcp``

Displays all connections, listening ports and FQDN for remote addresses.

``netstat -af``

Displays all connections, listening ports and FQDN for remote addresses.Also returns the Process ID (PID) associated with each connection.

``netstat -afo``

Displays network sent / receive statistics every 5 seconds.

``netstat -et 5``

Displays detailed information for all network adapters.

``ipconfig /all``

Returns the IP address that has been assigned, allowing the IP address to be assigned to another device.

``ipconfig /release``

Obtains a new IP address from the DHCP server.

``ipconfig /renew``

Displays the contents of the DNS client resolver cache, which includes both entries preloaded from the local Hosts file and any recently obtained resource records for names resolved by the computer.

``ipconfig /displaydns``

Flushes the DNS resolver cache, removing all cached DNS entries.

``ipconfig /flushdns``

Traces the path that packets take from the computer to a specified destination over a network.

``tracert <host>``

Obtains domain name or IP address mapping for the supplied host.

``nslookup <host>``

Obtains domain name or IP address mapping for the supplied host using a different DNS resolver.

``nslookup <host> 8.8.8.8``

Obtains domain name or IP address mapping for the supplied host. The type=mx option is used to specify that the query type is a mail exchange (MX) record.

``nslookup -type=mx <host>``

Displays the MAC address, adapter name, and transport name for each network adapter on the computer.

``getmac -v``

Displays the IP routing table.

``route print``

Generates a wireless LAN (WLAN) report that contains information about the wireless adapters and connections.

``netsh wlan show wlanreport``

Displays the IP addresses that are assigned to the network adapters.

``netsh interface ip show addresses``

</details>

<details>
<summary><b><font size="+1">Files</font></b></summary>
</br>

Displays the files and folders of the specified directory.

``dir \\<host>\<file path>``

Searches the specified directory and all subdirectories for files that match the search criteria, and it displays a list of the files that it finds.

``dir /s <*file>``

Searches the specified directory and all subdirectories for files that match the search criteria, and it displays a list of the files that it finds without headers.

``dir /s /b <*file>``

Displays the file extension associations in Windows.

``assoc``
</details>

