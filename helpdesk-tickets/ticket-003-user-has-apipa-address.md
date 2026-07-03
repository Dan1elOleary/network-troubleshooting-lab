# Ticket 003: User Has APIPA Address

## Ticket Summary

User reports no network access. Workstation has a `169.254.x.x` APIPA address.

## Category

DHCP

## Priority

High

## Reported Symptoms

- User cannot access internet.
- User cannot access shared drives.
- Network icon shows limited connectivity.
- IP address starts with `169.254`.

## Troubleshooting Steps

1. Ran `ipconfig /all`.
2. Confirmed the workstation had an APIPA address.
3. Checked Ethernet/Wi-Fi connection.
4. Released current IP configuration.
5. Renewed DHCP lease.
6. Confirmed workstation received a valid IP address.
7. Tested default gateway.
8. Tested internet connectivity.

## Commands Used

```cmd
ipconfig /all
ipconfig /release
ipconfig /renew
ping 192.168.1.1
ping 8.8.8.8
```

## Findings

The workstation did not receive a valid DHCP address at first and assigned itself an APIPA address.

## Root Cause

The workstation failed to obtain a DHCP lease.

## Resolution

Renewed the DHCP lease and confirmed the workstation received a valid IP address from the network.

## Preventive Recommendation

If the issue affects multiple users, check the DHCP server, DHCP scope availability, switch port, VLAN, or router configuration.

## User-Facing Update

```text
Your computer was not receiving a valid network address. I renewed the network lease and confirmed your connection is working again.
```
