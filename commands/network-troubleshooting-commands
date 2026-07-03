# Network Troubleshooting Commands

## Purpose

This document lists common Windows network troubleshooting commands used by helpdesk and IT support technicians.

## Check IP Configuration

```cmd
ipconfig
```

Shows basic IP address information.

```cmd
ipconfig /all
```

Shows detailed network adapter information, including:

- IPv4 address
- Subnet mask
- Default gateway
- DNS servers
- DHCP enabled status
- MAC address
- Lease obtained time
- Lease expiration time

## Release and Renew DHCP Address

Release current DHCP address:

```cmd
ipconfig /release
```

Request a new DHCP address:

```cmd
ipconfig /renew
```

Use this when a computer has an incorrect IP address or cannot get a valid DHCP lease.

## Flush DNS Cache

```cmd
ipconfig /flushdns
```

Clears cached DNS entries from the local computer.

Use this when websites are not resolving correctly or old DNS records may be cached.

## Display DNS Cache

```cmd
ipconfig /displaydns
```

Displays locally cached DNS records.

## Test Local TCP/IP Stack

```cmd
ping 127.0.0.1
```

This tests the local TCP/IP stack.

If this fails, there may be a local networking stack issue.

## Test Local IP Address

```cmd
ping <local-ip-address>
```

Example:

```cmd
ping 192.168.1.25
```

This tests whether the local computer can communicate with its own assigned IP address.

## Test Default Gateway

```cmd
ping 192.168.1.1
```

This tests communication between the workstation and the local router or gateway.

If this fails, possible causes include:

- Disconnected Ethernet cable
- Wi-Fi issue
- Incorrect IP configuration
- Firewall issue
- Gateway/router issue

## Test External IP Connectivity

```cmd
ping 8.8.8.8
```

This tests internet connectivity without relying on DNS.

If this works but websites do not load by name, DNS may be the issue.

## Test DNS Resolution

```cmd
ping google.com
```

If this fails but `ping 8.8.8.8` works, DNS may be failing.

## DNS Lookup

```cmd
nslookup google.com
```

Shows which DNS server is being used and whether the domain resolves.

Example:

```cmd
nslookup microsoft.com
```

## Trace Route

```cmd
tracert google.com
```

Shows the path traffic takes to reach a destination.

Use this to identify where traffic stops or slows down.

## PowerShell Connectivity Test

```powershell
Test-NetConnection google.com
```

Test a specific port:

```powershell
Test-NetConnection google.com -Port 443
```

This is useful for checking web access over HTTPS.

## View Network Adapters

```powershell
Get-NetAdapter
```

Shows network adapter status.

## View IP Address Information

```powershell
Get-NetIPAddress
```

Shows IP address details.

## View DNS Client Server Addresses

```powershell
Get-DnsClientServerAddress
```

Shows DNS server settings.

## Reset Network Stack

Use carefully and document before running.

```cmd
netsh winsock reset
```

```cmd
netsh int ip reset
```

These commands can help when the Windows network stack is corrupted or misconfigured.

Restart the computer after running them.

## Common Troubleshooting Sequence

```cmd
ipconfig /all
ping 127.0.0.1
ping <local-ip>
ping <default-gateway>
ping 8.8.8.8
ping google.com
nslookup google.com
tracert google.com
```

## Documentation Standard

When using these commands in a ticket, document:

- Command used
- Result
- What the result means
- Next step taken
- Final resolution
