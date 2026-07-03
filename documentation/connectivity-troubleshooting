# Connectivity Troubleshooting

## Purpose

This document explains how to troubleshoot general network connectivity issues.

## Common Connectivity Symptoms

- User cannot access internet.
- User cannot access shared drives.
- User cannot connect to VPN.
- User cannot reach internal applications.
- User can access some sites but not others.
- Network is slow.
- Wi-Fi disconnects often.

## Troubleshooting Layers

A simple troubleshooting model:

```text
Physical connection
      ↓
Network adapter
      ↓
IP address
      ↓
Default gateway
      ↓
DNS
      ↓
External destination
```

## Step 1: Confirm the Issue

Ask:

- Is the issue affecting one user or multiple users?
- Is the user on Wi-Fi or Ethernet?
- When did the issue start?
- Can the user access any websites?
- Can the user access internal resources?
- Did anything recently change?

## Step 2: Check Physical/Wireless Connection

Check:

- Ethernet cable
- Wi-Fi connection
- Airplane mode
- Network adapter enabled
- Correct SSID
- Docking station connection
- VPN status

## Step 3: Check IP Configuration

```cmd
ipconfig /all
```

Confirm:

- Valid IPv4 address
- Correct subnet
- Default gateway present
- DNS servers present
- No APIPA address

## Step 4: Test Loopback

```cmd
ping 127.0.0.1
```

If this fails, the local TCP/IP stack may have an issue.

## Step 5: Test Default Gateway

```cmd
ping 192.168.1.1
```

If this fails, the issue may be local network connectivity.

## Step 6: Test Internet IP

```cmd
ping 8.8.8.8
```

If this works, internet connectivity exists.

## Step 7: Test DNS

```cmd
ping google.com
```

If this fails while pinging `8.8.8.8` works, DNS may be the issue.

## Step 8: Trace the Route

```cmd
tracert google.com
```

Use this to identify where traffic stops.

## Step 9: Test Port Connectivity

PowerShell example:

```powershell
Test-NetConnection google.com -Port 443
```

This tests HTTPS connectivity.

## Common Root Causes

| Symptom | Possible Root Cause |
|---|---|
| No IP address | DHCP issue |
| 169.254 address | DHCP unavailable |
| Can ping IP but not domain | DNS issue |
| Cannot ping gateway | Local network issue |
| Cannot access one site | Website, DNS, or firewall issue |
| Slow connection | Wi-Fi, bandwidth, DNS, routing, or device issue |
| Shared drive unavailable | DNS, permissions, VPN, or server issue |

## Ticket Documentation Example

```text
Confirmed issue affected one workstation. Checked IP configuration and verified the device had a valid IP address, gateway, and DNS server. Ping to gateway succeeded. Ping to 8.8.8.8 succeeded. Ping to google.com failed, indicating DNS resolution issue. Flushed DNS cache and confirmed website access was restored.
```
