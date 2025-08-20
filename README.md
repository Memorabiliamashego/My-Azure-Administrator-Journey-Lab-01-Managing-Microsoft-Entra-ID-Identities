# 🏗️ Azure Home Lab — Microsoft Entra ID (AZ-104 Lab 01)

![Azure](https://img.shields.io/badge/Azure-Administrator-blue)
![AZ-104](https://img.shields.io/badge/Exam-AZ--104-success)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)

This repository documents my **Azure Home Lab** journey while preparing for the **AZ-104: Microsoft Azure Administrator** certification.  
Each lab focuses on a specific Azure service, combining **hands-on learning**, **automation scripts**, **architecture diagrams**, and **lessons learned**.

---

## 📌 Lab Overview — Microsoft Entra ID

**Objective:**  
Set up **Microsoft Entra ID** (formerly Azure Active Directory) to manage **users**, **guest access**, and **security groups**.

**Key tasks:**
- Create and manage users in **Entra ID**
- Invite external guest users
- Create security groups and assign members
- Automate group/user creation using **PowerShell** and **Azure CLI**

---

## 🏗️ High-Level Architecture

<img width="1024" height="1024" alt="ChatGPT Image Aug 20, 2025, 10_47_49 AM" src="https://github.com/user-attachments/assets/61503382-5423-405a-8d0c-1fb96d95f48c" />



---

## ⚙️ Step-by-Step Setup

### **1. Create a Resource Group**
```bash
az group create \
  --name EntraLabRG \
  --location eastus
````

### **2. Create Users**

**PowerShell:**

```powershell
Connect-AzureAD
New-AzureADUser -DisplayName "John Doe" -PasswordProfile @{Password="P@ssw0rd123"} -UserPrincipalName "john.doe@yourtenant.onmicrosoft.com" -MailNickName "johndoe"
```

**Azure Portal:**
Navigate to:
**Microsoft Entra ID → Users → New User**

---

### **3. Invite Guest Users**

```powershell
New-AzureADMSInvitation `
  -InvitedUserEmailAddress "guest.user@example.com" `
  -SendInvitationMessage $true `
  -InviteRedirectUrl "https://myapps.microsoft.com"
```

---

### **4. Create Security Groups**

```powershell
New-AzureADGroup `
  -DisplayName "Developers" `
  -MailEnabled $false `
  -MailNickname "developers" `
  -SecurityEnabled $true
```

---

### **5. Assign Users to Groups**

```powershell
Add-AzureADGroupMember `
  -ObjectId "<Group_ObjectID>" `
  -RefObjectId "<User_ObjectID>"
```

---

## 🧰 Technologies Used

| Tool / Service         | Purpose                              |
| ---------------------- | ------------------------------------ |
| **Azure Portal**       | Manage resources via UI              |
| **Microsoft Entra ID** | Identity and access management       |
| **Azure CLI**          | Automate Azure management            |
| **PowerShell**         | Scripting users, groups, and invites |
| **draw\.io**           | Architecture diagram creation        |
| **Markdown**           | Documentation                        |

---

## 📸 Screenshots

| Task                      | Screenshot                                               |
| ------------------------- | -------------------------------------------------------- |
| User creation in Entra ID |

 <img width="1177" height="661" alt="image" src="https://github.com/user-attachments/assets/8c97aee2-6363-4fd2-a8a4-8c6df9c9fe3b" />
|

| Security group assignment | 
<img width="1901" height="552" alt="image" src="https://github.com/user-attachments/assets/6dbb8847-b277-4eed-9b4e-0edf983a99a7" />
|

---

## 🎯 Learning Outcomes

By completing this lab, I’ve learned how to:

* Set up and manage **Microsoft Entra ID** from scratch
* Automate **user and group creation** using scripts
* Invite and manage **guest users** securely
* Design clean **Azure architecture diagrams**
* Use **GitHub** to document cloud engineering projects professionally

---

## 🚀 Roadmap

* [x] Lab 01: Microsoft Entra ID — Users & Groups ✅
* [ ] Lab 02: Role-Based Access Control (RBAC)
* [ ] Lab 03: Azure Storage Accounts & Access Keys
* [ ] Lab 04: Azure Networking — VNETs, Subnets, NSGs
* [ ] Lab 05: Azure Virtual Machines Deployment

---

## 📚 Resources

* [AZ-104 Exam Skills Outline](https://learn.microsoft.com/en-us/certifications/exams/az-104/)
* [Microsoft Learn — Azure Administrator](https://learn.microsoft.com/en-us/training/courses/az-104t00)
* [Microsoft Entra ID Docs](https://learn.microsoft.com/en-us/azure/active-directory/)

---

## 🧑‍💻 Author

**Mpho Mashego**
🌐 [LinkedIn](https://www.linkedin.com/) • 🐙 [GitHub](https://github.com/memorabiliamashego)

