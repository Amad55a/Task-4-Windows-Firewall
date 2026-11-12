# Task 4 — Setup and Use a Firewall

## Overview
This project documents a beginner-level firewall exercise using Windows Defender Firewall with Advanced Security on Windows 11.

## Objectives
- Understand Windows Firewall.
- Learn about inbound rules and TCP ports.
- Create a rule to block incoming TCP port 23.
- Perform a basic connectivity test.
- Document the results and limitations.

## Lab Environment
- Operating System: Windows 11
- Firewall: Windows Defender Firewall with Advanced Security
- Command: `wf.msc`
- Protocol: TCP
- Port: 23 (Telnet)

## Firewall Rule Configuration

| Setting | Value |
|---|---|
| Rule Name | Block_Inbound_Telnet_Port_23 |
| Direction | Inbound |
| Protocol | TCP |
| Local Port | 23 |
| Action | Block |
| Profiles | Domain, Private, Public |
| Enabled | Yes (during testing) |

## Testing and Results

A PowerShell TCP listener was started on port 23.

The command:

`Test-NetConnection 127.0.0.1 -Port 23`

returned:

`TcpTestSucceeded : True`

This confirms a successful local connection to the test listener. It does not prove that an external incoming connection was blocked.

An Ubuntu WSL connection attempt timed out. This result was inconclusive because WSL networking may affect connectivity.

No second physical device was available for an external firewall test.

## Conclusion

The inbound TCP port 23 blocking rule was created and inspected. The localhost test succeeded, but external firewall blocking was not independently verified. These limitations are included to ensure accurate reporting.

## Screenshots

Screenshots will be added to the `screenshots` folder:
- Firewall dashboard
- Inbound rules
- Firewall rule properties
- PowerShell test output

## Detailed Report

See `report/Task-4-Firewall-Report.md`.
