**Basic Firewall Rule Implementation (Windows/Linux)**

## **Objective:**
Implement and test firewall rules to block ICMP (ping) and restrict access to specific ports.

## **Tools Required:**
- **Windows:** Windows Defender Firewall
- **Linux:** UFW (Uncomplicated Firewall)

---

## **Step 1: Block ICMP (Ping) Requests**

### **Windows:**
1. Open **Windows Defender Firewall with Advanced Security**.
2. Click on **Inbound Rules > New Rule**.
3. Select **Custom** and click **Next**.
4. Choose **All Programs** and click **Next**.
5. In **Protocol and Ports**, select **ICMPv4**.
6. Click **Next**, select **Block the connection**, and apply to all profiles.
7. Name the rule and click **Finish**.

### **Linux (UFW):**
Run the following command:
```bash
sudo ufw deny proto icmp from any to any
```
To verify:
```bash
ping google.com
```
Expected outcome: Request times out.

---

## **Step 2: Block a Specific Port (e.g., Port 80 - HTTP)**

### **Windows:**
1. Open **Windows Defender Firewall with Advanced Security**.
2. Click **Inbound Rules > New Rule**.
3. Select **Port** and click **Next**.
4. Choose **TCP**, enter **80**, and click **Next**.
5. Select **Block the connection**, apply to all profiles, and name the rule.

### **Linux (UFW):**
Run the following command:
```bash
sudo ufw deny 80/tcp
```
To verify:
```bash
curl -I http://example.com
```
Expected outcome: Connection fails.

---

## **Step 3: Verify and Document Findings**

### **Windows:**
To list all firewall rules:
```powershell
netsh advfirewall firewall show rule name=all
```

### **Linux:**
To check UFW rules:
```bash
sudo ufw status verbose
```

## **Results and Observations:**
| Test Case     | Expected Result        | Actual Result|
|---------------|------------------------|--------------|
| Block ICMP    | Ping request times out | ✅ / ❌      |
| Block Port 80 | HTTP connection fails  | ✅ / ❌      |

## **Screenshots:**
Attach screenshots of firewall rules and command outputs.
Step -1: Block ICMP
![Step - 1](https://github.com/user-attachments/assets/1b644573-4a49-44da-8527-1304cdcde0f8)
![Step - 2](https://github.com/user-attachments/assets/129705ae-f307-4f89-a658-2d8d32e8ed11)
![Step - 3](https://github.com/user-attachments/assets/344292a8-f5bd-4c43-87bb-008262b2c4d7)
![Step - 4](https://github.com/user-attachments/assets/e3c83797-da47-452e-938f-090c4aebf154)
![Step - 5](https://github.com/user-attachments/assets/3458362c-dc8e-4bbd-8f9b-9542728f0123)
![Step - 6](https://github.com/user-attachments/assets/086e7d48-e217-45fa-9162-43e0f7ec485e)
![Step - 7](https://github.com/user-attachments/assets/9b1e88b9-8cd5-475a-9b90-3e4e5f0d249d)
![Step - 8](https://github.com/user-attachments/assets/73985b29-6549-4e85-8501-0388d86528eb)
![Step - 9](https://github.com/user-attachments/assets/2d67d6bc-3e0e-4bcb-973a-17420ea3bff0)
Step -2: Block a Specific Port
![Step - 1](https://github.com/user-attachments/assets/bcb56757-ca07-43f6-8595-ef1e17fce494)
![Step - 2](https://github.com/user-attachments/assets/fd0efe4f-64a5-4980-8a3d-708c2197a2f5)
![Step - 3](https://github.com/user-attachments/assets/3dbf36f4-64d7-4e85-9813-04ae2f05ee4c)
![Step - 4](https://github.com/user-attachments/assets/97c1c50d-2b96-47bf-9b66-12b5b8326d95)
![Step - 5](https://github.com/user-attachments/assets/3c190b07-9e4e-4ad4-a840-81017e3312bd)
![Step - 6](https://github.com/user-attachments/assets/cc4571bd-b4d5-4a62-a337-efd32d296b5f)
![Step - 7](https://github.com/user-attachments/assets/2b7ec8fd-550d-4b35-a4f7-6281ca5763b1)
Step -3: Verify and Document Findings
![CMD output for Firewall Block](https://github.com/user-attachments/assets/d7178fd5-175d-47f7-b208-42ff2bec8739)
---

## **Conclusion:**
Summarize key findings and effectiveness of the firewall rules implemented.
