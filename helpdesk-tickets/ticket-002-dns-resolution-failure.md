# Ticket 002: DNS Resolution Failure

## Ticket Summary

User can access websites by IP address but cannot access websites by domain name.

## Category

DNS

## Priority

Medium

## Reported Symptoms

- User cannot browse to websites by name.
- User can ping external IP address.
- User receives DNS-related browser error.

## Troubleshooting Steps

1. Ran `ipconfig /all`.
2. Confirmed DNS server settings.
3. Pinged external IP address.
4. Pinged domain name.
5. Ran `nslookup`.
6. Flushed DNS cache.
7. Tested name resolution again.

## Commands Used

```cmd
ipconfig /all
ping 8.8.8.8
ping google.com
nslookup google.com
ipconfig /flushdns
```

## Findings

The workstation could reach an external IP address, but domain names were not resolving properly.

## Root Cause

DNS resolution failure.

## Resolution

Flushed DNS cache and verified DNS server settings. After troubleshooting, domain names resolved successfully.

## Preventive Recommendation

Monitor whether the issue affects other users. If multiple users are affected, escalate to network or systems administration for DNS server review.

## User-Facing Update

```text
The issue was related to name resolution. I cleared the DNS cache and verified that websites are loading by name again.
```
