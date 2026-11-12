# Task 4: Setup and Use a Firewall

## 1. Introduction

A firewall is a security system that monitors and controls network traffic entering and leaving a computer. It helps protect a computer from unauthorized network connections.

For this task, I used Windows Defender Firewall on Windows 11.

## 2. Tools Used

- Windows 11
- Windows Defender Firewall with Advanced Security
- PowerShell
- Ubuntu on WSL for an additional connection attempt

## 3. Procedure

### Step 1: Open Windows Firewall

I opened the Run dialog using Windows + R and entered:

`wf.msc`

This opened Windows Defender Firewall with Advanced Security.

### Step 2: Inspect Inbound Rules

I selected Inbound Rules to view the rules controlling incoming network connections.

### Step 3: Create a Blocking Rule

I created a temporary rule with these settings:

- Name: Block_Inbound_Telnet_Port_23
- Rule type: Port
- Protocol: TCP
- Local port: 23
- Action: Block the connection
- Profiles: Domain, Private, Public

The rule was enabled during testing.

### Step 4: Start a Test Listener

I used PowerShell to start a TCP listener on port 23.

### Step 5: Test the Local Connection

I ran:

`Test-NetConnection 127.0.0.1 -Port 23`

The result was:

`TcpTestSucceeded : True`

This showed that the local TCP connection succeeded. A localhost test does not establish whether the firewall blocks connections from other devices.

### Step 6: Attempt an Additional Test

I attempted to connect from Ubuntu WSL to the Windows host. The attempt timed out.

This result was inconclusive because WSL network routing may affect the connection.

I did not have a second physical device available for an external test.

## 4. Results

The temporary inbound rule was successfully created and enabled.

The local TCP connection test succeeded. However, an external connection test was not completed, so I cannot claim that external blocking was verified.

## 5. Conclusion

This task helped me understand how Windows Defender Firewall controls incoming network traffic and how inbound port rules work.

I learned that TCP port 23 is commonly used by Telnet and that Telnet does not encrypt its communication by default.

I also learned that a successful localhost test is different from testing an incoming connection from another device.

## 6. Further Improvements

- Repeat the test using a second computer on the same network.
- Compare the connection result with the firewall rule enabled and disabled.
- Capture screenshots of the configuration and test results.
- Remove temporary test configurations after the lab.

## 7. Safety and Cleanup

The test listener and temporary firewall rule are for laboratory use only. Stop the listener and remove the temporary rule when testing and screenshots are complete, unless the rule is intentionally required for another authorized test.
