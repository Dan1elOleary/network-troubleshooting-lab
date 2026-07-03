# DNS Troubleshooting

## Purpose

This document explains how to troubleshoot common DNS issues in a Windows IT support environment.

## What DNS Does

DNS converts domain names into IP addresses.

Example:

```text
google.com → IP address
```

Without DNS, users may not be able to reach websites by name even if the internet connection is working.

## Common DNS Symptoms

- User cannot access websites by name.
- User can ping an IP address but not a domain name.
- Browser says DNS server not responding.
- Certain websites fail to load.
- Internal company resources do not resolve.
- VPN-connected users cannot resolve internal names.

## Common DNS Causes

Possible causes include:

- Incorrect DNS server configured
- DNS server unavailable
- DNS cache issue
- Incorrect VPN DNS settings
- Router DNS problem
- ISP DNS issue
- Local hosts file issue
- Old cached DNS record

## DNS Troubleshooting Steps

### Step 1: Check IP Configuration

```cmd
ipconfig /all
```

Review the DNS server listed under the active network adapter.

### Step 2: Test External IP

```cmd
ping 8.8.8.8
```

If this works, the computer likely has internet access.

### Step 3: Test Name Resolution

```cmd
ping google.com
```

If this fails while pinging an IP works, DNS may be the issue.

### Step 4: Use nslookup

```cmd
nslookup google.com
```

Check:

- Which DNS server responds
- Whether the name resolves
- Whether there is a timeout

### Step 5: Flush DNS Cache

```cmd
ipconfig /flushdns
```

Then test again:

```cmd
nslookup google.com
```

### Step 6: Try Another DNS Server

For lab testing only, you may test with another DNS server.

Example public DNS servers:

```text
8.8.8.8
1.1.1.1
```

In a business environment, follow company policy before changing DNS settings.

## Example Issue

### Symptom

User can ping `8.8.8.8`, but cannot open websites by name.

### Finding

External IP connectivity works, but DNS resolution fails.

### Likely Root Cause

DNS server issue or incorrect DNS configuration.

### Resolution

Flush DNS cache, verify DNS server settings, and confirm DNS resolution with `nslookup`.

## Commands Used

```cmd
ipconfig /all
ping 8.8.8.8
ping google.com
nslookup google.com
ipconfig /flushdns
```

## Ticket Documentation Example

```text
User reported websites would not load. Confirmed the workstation could ping 8.8.8.8 but could not resolve google.com. Ran nslookup and confirmed DNS resolution failure. Flushed DNS cache and verified DNS server settings. After DNS cache was cleared, websites loaded successfully.
```
