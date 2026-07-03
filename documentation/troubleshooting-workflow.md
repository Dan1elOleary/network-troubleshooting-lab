# Network Troubleshooting Workflow

## Purpose

This document provides a repeatable workflow for handling network troubleshooting tickets.

## Helpdesk Network Troubleshooting Workflow

```text
1. Gather user details.
2. Confirm the scope of the issue.
3. Check connection type.
4. Review IP configuration.
5. Test local TCP/IP.
6. Test gateway connectivity.
7. Test external IP connectivity.
8. Test DNS resolution.
9. Apply fix.
10. Confirm resolution with user.
11. Document the ticket.
```

## Step 1: Gather User Details

Collect:

- User name
- Device name
- Location
- Connection type
- Error message
- Time issue started
- Applications or websites affected

## Step 2: Determine Scope

Ask:

- Is this affecting one user or multiple users?
- Is it only one website or all websites?
- Is it only Wi-Fi or also Ethernet?
- Is the user on VPN?
- Is the user remote or onsite?

## Step 3: Check IP Configuration

Run:

```cmd
ipconfig /all
```

Document:

- IP address
- Subnet mask
- Default gateway
- DNS server
- DHCP enabled
- DHCP server

## Step 4: Test Connectivity

Run:

```cmd
ping 127.0.0.1
ping <default-gateway>
ping 8.8.8.8
ping google.com
```

## Step 5: Test DNS

Run:

```cmd
nslookup google.com
```

If DNS fails, try:

```cmd
ipconfig /flushdns
```

## Step 6: Trace Route

Run:

```cmd
tracert google.com
```

Use this when the connection is slow or stops before reaching the destination.

## Step 7: Apply Fix

Possible fixes:

- Reconnect Wi-Fi
- Reseat Ethernet cable
- Disable and re-enable adapter
- Renew DHCP lease
- Flush DNS cache
- Correct DNS settings
- Restart device
- Restart router or escalate to network team
- Check VPN connection
- Escalate if multiple users are affected

## Step 8: Confirm Resolution

Confirm with the user:

- Website loads
- Application connects
- Shared drive works
- VPN connects
- Network speed is acceptable

## Step 9: Document Ticket

Document:

- Issue summary
- User affected
- Device affected
- Commands used
- Results observed
- Root cause
- Resolution
- Preventive recommendation

## Escalation Criteria

Escalate when:

- Multiple users are affected
- Gateway is unreachable for multiple devices
- DHCP server is not assigning addresses
- DNS server is unavailable
- Network outage is suspected
- Firewall or routing issue is suspected
- ISP issue is suspected
- Switch, router, or access point issue is suspected
