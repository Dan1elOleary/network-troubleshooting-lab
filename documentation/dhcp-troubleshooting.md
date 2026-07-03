# DHCP Troubleshooting

## Purpose

This document explains how to troubleshoot DHCP-related issues in a Windows environment.

## What DHCP Does

DHCP automatically assigns network settings to a device.

DHCP can provide:

- IP address
- Subnet mask
- Default gateway
- DNS server
- Lease duration

## Common DHCP Symptoms

- Computer has no internet access.
- Computer has an APIPA address.
- IP address starts with `169.254`.
- User cannot access network resources.
- Device says unidentified network.
- Device cannot reach the default gateway.

## What Is APIPA?

APIPA stands for Automatic Private IP Addressing.

A Windows computer may assign itself an IP address starting with:

```text
169.254.x.x
```

This usually means the computer could not contact a DHCP server.

## Common DHCP Causes

Possible causes include:

- DHCP server unavailable
- Network cable unplugged
- Wi-Fi disconnected
- VLAN issue
- DHCP scope exhausted
- Router issue
- Network adapter problem
- Device on wrong network
- DHCP service stopped

## DHCP Troubleshooting Steps

### Step 1: Check IP Configuration

```cmd
ipconfig /all
```

Look for:

- IPv4 address
- Default gateway
- DHCP enabled
- DHCP server
- Lease obtained
- Lease expires

### Step 2: Identify APIPA

If the IP address starts with:

```text
169.254
```

The computer likely did not receive a DHCP address.

### Step 3: Release Current Address

```cmd
ipconfig /release
```

### Step 4: Renew DHCP Address

```cmd
ipconfig /renew
```

### Step 5: Check Network Connection

Confirm:

- Ethernet cable is connected
- Wi-Fi is connected
- Correct network is selected
- Adapter is enabled
- Router/switch is online

### Step 6: Test Gateway

```cmd
ping <default-gateway>
```

Example:

```cmd
ping 192.168.1.1
```

## Example Issue

### Symptom

User cannot access the internet. `ipconfig` shows `169.254.10.25`.

### Finding

The computer has an APIPA address and no default gateway.

### Likely Root Cause

The device did not receive a DHCP lease.

### Resolution

Confirmed network connection, released and renewed IP address, and verified the device received a valid IP address.

## Commands Used

```cmd
ipconfig /all
ipconfig /release
ipconfig /renew
ping 192.168.1.1
```

## Ticket Documentation Example

```text
User reported no internet access. Reviewed IP configuration and found the workstation had a 169.254.x.x APIPA address. Released and renewed the DHCP lease. After renewal, the workstation received a valid 192.168.1.x address with a default gateway. Confirmed internet access was restored.
```
