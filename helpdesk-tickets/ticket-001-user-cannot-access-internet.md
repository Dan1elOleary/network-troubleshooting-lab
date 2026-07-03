# Ticket 001: User Cannot Access Internet

## Ticket Summary

User reports they cannot access the internet from their workstation.

## Category

Network Connectivity

## Priority

Medium

## Reported Symptoms

- User cannot open websites.
- Browser shows connection error.
- Other applications may still open locally.
- Issue appears limited to one workstation.

## Troubleshooting Steps

1. Confirmed issue with the user.
2. Checked whether the user was connected through Wi-Fi or Ethernet.
3. Ran `ipconfig /all`.
4. Confirmed the workstation had a valid IP address.
5. Pinged loopback address.
6. Pinged default gateway.
7. Pinged external IP address.
8. Tested DNS resolution.
9. Flushed DNS cache.
10. Confirmed websites loaded successfully.

## Commands Used

```cmd
ipconfig /all
ping 127.0.0.1
ping 192.168.1.1
ping 8.8.8.8
ping google.com
ipconfig /flushdns
```

## Findings

The workstation had a valid IP address and could reach the default gateway. External IP connectivity worked, but DNS name resolution was inconsistent.

## Root Cause

Local DNS cache issue.

## Resolution

Flushed the DNS cache and confirmed the user could access websites again.

## Preventive Recommendation

If the issue returns, review DNS server configuration and check whether other users are experiencing similar DNS issues.

## User-Facing Update

```text
I cleared the local DNS cache and confirmed the workstation can access websites again. Please let IT know if the issue returns.
```
