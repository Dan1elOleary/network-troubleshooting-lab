# Network Troubleshooting Lab

## Overview

This project is a networking troubleshooting lab designed to demonstrate practical IT support skills related to DNS, DHCP, TCP/IP, gateway connectivity, IP addressing, ping tests, traceroute, network documentation, and helpdesk-style troubleshooting.

The purpose of this project is to show how common network issues can be identified, tested, documented, and resolved using standard Windows networking tools.

This project is useful for helpdesk, desktop support, IT support, MSP technician, junior systems administrator, and entry-level networking roles.

## Project Status

This project is currently a documentation and troubleshooting workflow project. The commands, ticket examples, and troubleshooting notes are written as a portfolio lab to demonstrate practical networking support knowledge.

Screenshots can be added after testing these commands in a Windows lab environment.

## Skills Demonstrated

- Basic TCP/IP troubleshooting
- DNS troubleshooting
- DHCP troubleshooting
- Gateway connectivity testing
- Internet connectivity testing
- Local network troubleshooting
- Command-line network diagnostics
- Helpdesk ticket documentation
- Root cause analysis
- User-facing communication
- Technical documentation

## Tools Used

- Windows Command Prompt
- PowerShell
- ipconfig
- ping
- tracert
- nslookup
- Test-NetConnection
- Windows Network Settings
- Event Viewer
- GitHub
- Markdown

## Lab Scenario

This lab simulates common network issues in a small office or helpdesk environment.

Example issues include:

- User cannot access the internet
- DNS is not resolving websites
- Computer receives an APIPA address
- Default gateway is unreachable
- DHCP is not assigning an IP address
- User can access local resources but not websites
- User can access websites by IP address but not by name
- Network adapter needs to be reset
- Cached DNS records cause connection problems

## Core Troubleshooting Method

The basic troubleshooting process used in this lab is:

```text
1. Confirm the user's issue.
2. Identify the affected device.
3. Check physical or wireless connection.
4. Review IP configuration.
5. Test loopback address.
6. Test local IP address.
7. Test default gateway.
8. Test DNS resolution.
9. Test external connectivity.
10. Document root cause and resolution.
```

## Common Commands Used

| Command | Purpose |
|---|---|
| `ipconfig /all` | Shows full IP configuration |
| `ipconfig /release` | Releases DHCP address |
| `ipconfig /renew` | Requests a new DHCP address |
| `ipconfig /flushdns` | Clears local DNS cache |
| `ping 127.0.0.1` | Tests local TCP/IP stack |
| `ping <gateway>` | Tests connection to default gateway |
| `ping 8.8.8.8` | Tests external IP connectivity |
| `ping google.com` | Tests DNS and internet connectivity |
| `nslookup google.com` | Tests DNS name resolution |
| `tracert google.com` | Shows route to destination |
| `Test-NetConnection` | PowerShell network connectivity test |

## Example Troubleshooting Flow

### Issue

User reports they cannot access the internet.

### Step 1: Check IP Configuration

```cmd
ipconfig /all
```

Review:

- IPv4 address
- Subnet mask
- Default gateway
- DNS servers
- DHCP enabled status

### Step 2: Test Local TCP/IP Stack

```cmd
ping 127.0.0.1
```

If this fails, the issue may be related to the local TCP/IP stack.

### Step 3: Test Default Gateway

```cmd
ping 192.168.1.1
```

If this fails, the issue may be between the computer and the local network.

### Step 4: Test External IP

```cmd
ping 8.8.8.8
```

If this works but websites do not load, DNS may be the issue.

### Step 5: Test DNS

```cmd
nslookup google.com
```

If DNS fails, check DNS server settings or flush DNS cache.

## Common Network Issues Covered

| Issue | Possible Cause |
|---|---|
| No internet access | Gateway, DNS, DHCP, adapter, ISP, Wi-Fi, firewall |
| APIPA address | DHCP server unreachable |
| DNS failure | Incorrect DNS server or DNS cache issue |
| Gateway unreachable | Local network issue |
| Slow connection | Wi-Fi signal, DNS delay, bandwidth, routing issue |
| Cannot access one website | Website issue, DNS issue, browser cache, firewall |
| Can ping IP but not name | DNS issue |
| Can access local network but not internet | Gateway or routing issue |

## Repository Structure

```text
network-troubleshooting-lab/
├── README.md
├── lab-diagram.md
├── commands/
│   └── network-troubleshooting-commands.md
├── documentation/
│   ├── dns-troubleshooting.md
│   ├── dhcp-troubleshooting.md
│   ├── connectivity-troubleshooting.md
│   └── troubleshooting-workflow.md
├── helpdesk-tickets/
│   ├── ticket-001-user-cannot-access-internet.md
│   ├── ticket-002-dns-resolution-failure.md
│   └── ticket-003-user-has-apipa-address.md
└── screenshots/
    └── README.md
```

## What I Learned

This project helped me document a structured approach to network troubleshooting. I practiced identifying whether a network issue is related to local TCP/IP, DHCP, DNS, the default gateway, internet routing, or user device configuration.

The lab also demonstrates how to document network issues in a helpdesk-friendly format, including symptoms, troubleshooting steps, root cause, resolution, and preventive recommendations.

## Relevance to IT Roles

This project is relevant to:

- Helpdesk Technician
- IT Support Specialist
- Desktop Support Technician
- Technical Support Engineer
- MSP Technician
- Junior Systems Administrator
- Entry-Level Network Technician
- Cybersecurity Analyst with network troubleshooting responsibilities

## Future Improvements

Planned improvements include:

- Add screenshots of command output.
- Add Wireshark packet capture examples.
- Add DNS lookup screenshots.
- Add DHCP lease troubleshooting examples.
- Add network diagram images.
- Add Windows Event Viewer network logs.
- Add router/gateway troubleshooting notes.
- Add PowerShell network testing examples.
