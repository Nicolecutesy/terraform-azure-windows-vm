# 🚀 Terraform Azure Windows VM Project

This project uses **Terraform** to deploy a complete Azure infrastructure environment that includes a Windows Server Virtual Machine. It was created as part of a hands-on learning initiative to strengthen Infrastructure-as-Code (IaC) and cloud automation skills.

---

## 🔧 What This Project Does

- Provisions a new **Azure Resource Group**
- Creates a **Virtual Network** and **Subnet**
- Deploys a **Network Security Group (NSG)** with custom rules (RDP, HTTP, SSH)
- Assigns a **Dynamic Public IP Address**
- Creates a **Network Interface Card (NIC)**
- Deploys a **Windows Server 2019 VM** with:
  - RDP access enabled via PowerShell script
  - IIS Web Server auto-installed on startup

---

## 🧱 Technologies Used

- Terraform v1.3+
- Azure CLI
- Azure Resource Manager (ARM)
- PowerShell (for custom_data VM setup)

---

## 📁 File Structure

```
terraform-azure-windows-vm/
├── main.tf               # Main infrastructure definition
├── providers.tf          # Provider configuration for Azure
├── .gitignore            # Ignore Terraform local state & cache
├── .terraform.lock.hcl   # Terraform dependency lock file
```

---

## 🛠️ How to Use This Project

### 1. Authenticate to Azure
```bash
az login
```

### 2. Initialize Terraform
```bash
terraform init
```

### 3. Preview the Plan
```bash
terraform plan
```

### 4. Apply the Infrastructure
```bash
terraform apply
```
Type `yes` to confirm.

### 5. Get the Public IP & Connect
Use the IP shown in Azure or use the Azure CLI:
```bash
az vm list-ip-addresses -g rg-terraform-lab -n winvm-lab --output table
```
Use RDP to connect using:
- **Username:** nicoleadmin
- **Password:** (set in `main.tf`)

---

## 🖥️ Inside the VM
- RDP is enabled via PowerShell
- Windows Firewall allows port 3389 and 80
- IIS is auto-installed and runs on port 80
- Browse to `http://<public-ip>` to see the IIS Welcome page

---

## 🧠 Key Concepts Demonstrated

- Infrastructure-as-Code (IaC)
- Dynamic resource provisioning
- Azure networking and security
- VM bootstrap with PowerShell + `custom_data`
- Real-world troubleshooting of RDP + NSG + Firewall

---

## 🙌 Author
**Nicole Cutesy**  
Cloud & DevOps Enthusiast | Cybersecurity Learner | Women in Tech  

GitHub: [Nicolecutesy](https://github.com/Nicolecutesy)

---

> 💡 _This project was completed as part of a portfolio to demonstrate Azure and Terraform hands-on capabilities._
