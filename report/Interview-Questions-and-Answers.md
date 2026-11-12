# Task 4 – Firewall Interview Questions and Answers

## 1. What is a firewall?
A firewall is a security system that monitors and controls incoming and outgoing network traffic based on security rules. It helps prevent unauthorized access to computers and networks.

## 2. Difference between stateful and stateless firewalls
- **Stateful firewall:** Tracks active connections and checks whether packets belong to an existing permitted connection.
- **Stateless firewall:** Checks each packet independently without remembering previous packets or connections.

## 3. What are inbound and outbound rules?
- **Inbound rules:** Control traffic entering a computer.
- **Outbound rules:** Control traffic leaving a computer.

## 4. How does UFW simplify firewall management?
UFW means Uncomplicated Firewall. It is a Linux firewall management tool that makes it easier to create and manage firewall rules using simple commands.

Examples:
```bash
sudo ufw enable
sudo ufw status
sudo ufw allow 22/tcp
sudo ufw deny 23/tcp
```

## 5. Why block port 23 (Telnet)?
Telnet commonly uses TCP port 23. It does not encrypt communication by default, so usernames and passwords can be exposed. Blocking it reduces unnecessary security risks.

## 6. What are common firewall mistakes?
- Allowing unnecessary ports.
- Creating overly broad rules.
- Forgetting to enable the firewall.
- Blocking important services accidentally.
- Not reviewing firewall rules.
- Ignoring logs.
- Failing to test rules.

## 7. How does a firewall improve network security?
A firewall blocks unauthorized connections, controls network traffic, restricts unnecessary ports, and reduces exposure to network attacks.

## 8. What is NAT in firewalls?
NAT means Network Address Translation. It translates IP addresses in network packets. For example, it allows multiple devices on a private network to share one public IP address when accessing the internet.

## Practical work completed
- Used Windows Defender Firewall with Advanced Security.
- Created an inbound rule named `Block_Inbound_Telnet_Port_23`.
- Selected TCP port 23.
- Set the action to Block.
- Selected Domain, Private, and Public profiles.
- Enabled the rule during the test.

## Testing limitation
A successful connection to `127.0.0.1` tests the local computer's loopback connection. It does not prove that an external device is blocked by the firewall. An external connection test was not successfully completed.

## Conclusion
This task provided practical experience with Windows Firewall, inbound rules, TCP ports, and basic network security concepts.
