
## 🔐 TASK GOAL:

Set up and test firewall rules on either Windows or Linux (UFW) to allow/block traffic.

---

## ⚙️ CHOOSE YOUR PLATFORM:

🟩 If you're using Windows, follow Path A

---

## 🟩 PATH A: Windows Firewall – Step-by-Step

### 🔹 Step 1: Open Windows Firewall

1. Press Win + S and search for:
   Windows Defender Firewall with Advanced Security
2. Click on it to open.

---

### 🔹 Step 2: View Current Rules

* On the left, click on:

  * Inbound Rules
  * Outbound Rules

Scroll through to see what's already allowed/blocked.

---

### 🔹 Step 3: Block Port 23 (Telnet)

1. Click Inbound Rules > New Rule
2. Choose Port > Click Next
3. Select TCP > Enter 23 > Next
4. Select Block the connection > Next
5. Apply to all profiles > Next
6. Name it "Block Telnet Port 23" > Finish

📸 Take a screenshot of this rule.

---

### 🔹 Step 4: Test the Rule

Use telnet to test:

1. Press Win + R, type cmd
2. Run:

  
cmd

   telnet localhost 23
   
   * It should fail to connect, showing the rule is working.

---

### 🔹 Step 5: Remove the Rule

* Go to Inbound Rules
* Right-click your Block Telnet rule > Delete

📸 Take a screenshot again to show it’s removed.

---

### 🔹 Step 6: Create GitHub Repo

1. Create a new GitHub repository:
   task-4-firewall
2. Add:

   * Screenshots
   * Short README.md file explaining:

     * What you did
     * What port 23 is (Telnet)
     * Why firewalls block unused ports



* Screenshot:

  * Initial rules
  * Rule added
  * Test result
  * Rule removed
* Upload all to GitHub repo with a README

