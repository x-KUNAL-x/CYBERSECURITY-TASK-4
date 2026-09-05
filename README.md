# 🛡️ CYBERSECURITY-TASK-4

## Task 4: Setup and Use a Firewall on Windows/Linux

### 📌 Objective

The objective of this task is to understand how a firewall controls network traffic and to configure basic firewall rules to **allow or block incoming and outgoing connections**.

In this task, firewall rules are reviewed, a test rule is created to block a specific port, the rule is tested, and the configuration is restored to its original state.

---

## 🧰 Tools Used

* **Windows Firewall** – For managing firewall rules on Windows
* **UFW (Uncomplicated Firewall)** – Alternative firewall management tool for Linux
* **Command Prompt / PowerShell** – For checking and testing network connectivity

---

## 📋 Task Requirements

The following activities were performed as part of this task:

1. Open the firewall configuration tool.
2. Review the existing firewall rules.
3. Create a rule to block inbound traffic on a specific port.
4. Test whether the port is blocked.
5. Understand how firewall rules allow or deny traffic.
6. Remove the temporary test rule.
7. Restore the firewall configuration.
8. Document the firewall configuration and testing process.

---

## 🔥 Firewall Overview

A **firewall** is a security mechanism that monitors and controls network traffic based on predefined rules.

It can:

* Allow trusted network connections
* Block unauthorized connections
* Control inbound and outbound traffic
* Restrict access to specific ports
* Reduce the attack surface of a computer
* Help prevent unauthorized network access

For example, **port 23** is commonly associated with Telnet. Since Telnet is an insecure protocol, blocking unnecessary access to port 23 can reduce potential security risks.

---

## 🪟 Windows Firewall

### Step 1: Open Windows Firewall

Open **Windows Defender Firewall with Advanced Security**.

It can be opened by searching for:

```text
Windows Defender Firewall with Advanced Security
```

The interface provides access to:

* Inbound Rules
* Outbound Rules
* Connection Security Rules
* Monitoring

---

### Step 2: Review Existing Rules

The **Inbound Rules** section was inspected to understand the currently configured rules.

Firewall rules can specify:

* Program
* Protocol
* Local port
* Remote port
* IP address
* Action
* Profile

---

### Step 3: Create a Test Block Rule

A temporary inbound rule can be created to block **TCP port 23**.

Example configuration:

```text
Rule Type: Port
Protocol: TCP
Local Port: 23
Action: Block the connection
Profiles: Domain, Private, Public
Name: Block-Test-Port-23
```

> This is a controlled test rule. The rule should only be created on a system where you are authorized to modify firewall settings.

---

### Step 4: Test the Rule

After creating the rule, connectivity to the selected port can be tested using an appropriate network testing command.

Example:

```cmd
Test-NetConnection 127.0.0.1 -Port 23
```

If PowerShell is available, the command can be executed from PowerShell.

A blocked result indicates that the firewall rule is preventing the connection.

---

### Step 5: Remove the Test Rule

After testing, the temporary firewall rule should be removed.

This restores the firewall configuration and prevents the test rule from unnecessarily affecting future network connections.

---

## 🐧 Linux / UFW Alternative

On Linux systems using UFW, firewall rules can be managed from the terminal.

### Check Firewall Status

```bash
sudo ufw status
```

### Block Port 23

```bash
sudo ufw deny 23/tcp
```

### Allow SSH

If SSH is required:

```bash
sudo ufw allow 22/tcp
```

### Remove the Test Rule

```bash
sudo ufw delete deny 23/tcp
```

> SSH should only be enabled when it is required and properly secured.

---

## 🧪 Testing and Verification

The firewall configuration should be verified before and after applying the test rule.

| Test                  | Expected Result                                  |
| --------------------- | ------------------------------------------------ |
| Review firewall rules | Existing rules are displayed                     |
| Block TCP port 23     | Traffic to the test port is denied               |
| Test connection       | Connection should fail if the block is effective |
| Remove test rule      | Temporary rule is removed                        |
| Check rules again     | Firewall returns to the previous configuration   |

---

## 📸 Evidence / Screenshots

Screenshots can be added to document the practical work.

Recommended screenshots:

```text
Screenshots/
├── firewall-rules.png
├── block-port-rule.png
└── firewall-test.png
```

### Screenshot 1 – Firewall Rules

Shows the firewall management interface and existing rules.

### Screenshot 2 – Block Rule

Shows the temporary rule created to block TCP port 23.

### Screenshot 3 – Test Result

Shows the connection test demonstrating that the selected port is blocked.

---

## 🔐 Security Considerations

Firewall configuration is an important part of system security.

Good practices include:

* Block unnecessary ports and services.
* Allow only required network traffic.
* Avoid exposing services directly to untrusted networks.
* Review firewall rules regularly.
* Remove temporary testing rules after testing.
* Use secure protocols such as SSH instead of Telnet.
* Keep the operating system and security software updated.
* Avoid disabling the firewall without a valid reason.

---

## 📚 What I Learned

Through this task, I learned:

* How firewalls control network traffic.
* How to inspect existing firewall rules.
* How inbound traffic can be blocked using firewall rules.
* How ports and protocols are used in firewall configuration.
* How to test whether a firewall rule is working.
* Why unnecessary open ports can increase security risks.
* How Windows Firewall and UFW can be used for basic firewall management.

---

## 📁 Project Structure

```text
CCYBERSECURITY-TASK-4/
│
├── README.md
│
├── Firewall-Rules/
│   ├── Inbound-Rules.txt
│   └── Outbound-Rules.txt
│
└── Screenshots/
    ├── firewall-main.png
    ├── inbound-rules.png
    ├── outbound-rules.png
    ├── block-port-rule.png
    └── firewall-test.png
```

---

## ⚠️ Disclaimer

This task was performed for **educational and cybersecurity learning purposes** in an authorized environment.

Firewall rules should only be modified on systems and networks that you own or have permission to administer.
