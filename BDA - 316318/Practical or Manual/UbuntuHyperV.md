
---

# 🐧 Install Ubuntu on Hyper-V (Windows)

---

## 1️⃣ Prerequisites

* 🖥️ **Windows Edition**: Windows 10/11 **Pro, Education, or Enterprise**
* ⚙️ **Virtualization** enabled in BIOS/UEFI
* 💾 **RAM**:

  * Recommended: **8 GB or more**
  * Minimum: **4 GB**

---

## 2️⃣ Enable Hyper-V

1. 🔍 Press **Win + S**
2. Type **Turn Windows features on or off**
3. Enable:

   * ☑️ **Hyper-V**

     * Hyper-V Management Tools
     * Hyper-V Platform
4. ✅ Click **OK**
5. 🔄 Restart your PC

---

## 3️⃣ Open Hyper-V Manager

1. 🔍 Press **Win + S**
2. Type **Hyper-V Manager**
3. ▶️ Open the application

---

## 4️⃣ Download Ubuntu ISO

1. 🌐 Go to **[https://ubuntu.com](https://ubuntu.com)**
2. ⬇️ Download **Ubuntu Desktop LTS**
3. 💾 Save the `.iso` file to a known location

---

## 5️⃣ Create the Ubuntu Virtual Machine

### 5.1 ➕ Create New VM

1. In **Hyper-V Manager**, select your computer
2. In the right panel, click **New → Virtual Machine**

---

### 5.2 🧙 Virtual Machine Wizard Settings

Configure the wizard exactly as follows:

#### 🏷️ Name

* `Ubuntu`

#### 🧬 Generation

* ✅ **Generation 2**

#### 🧠 Memory

* Startup memory: **4096 MB**

  * Use **2048 MB** if RAM is limited
* ⚠️ Recommended:

  * ❌ Uncheck **Use Dynamic Memory for this virtual machine**

#### 🌐 Networking

* **Default Switch**

#### 💽 Virtual Hard Disk

* Use default settings
* Recommended size: **40–50 GB**

#### 📀 Installation Options

* Select **Install an operating system from a bootable image**
* Browse and select the Ubuntu **`.iso` file**

3. ✅ Click **Finish**

---

## 6️⃣ Start Ubuntu & Install

1. 🖱️ Right-click **Ubuntu**
2. 🔌 Click **Connect**
3. ▶️ Click **Start**
4. 🐧 When the Ubuntu screen appears, select:

   * **Try or Install Ubuntu**
5. 🧩 Complete the Ubuntu installation process

---

## 7️⃣ Fix Secure Boot Error (If Ubuntu Fails to Start)

If the VM fails to boot or shows a Secure Boot error, follow the steps below.

---

### 7.1 ⛔ Turn Off the VM

1. 🖱️ Right-click **Ubuntu**
2. ⛔ Click **Turn Off**

⚠️ **Do NOT select Restart**

---

### 7.2 ⚙️ Open VM Settings

1. 🖱️ Right-click **Ubuntu**
2. ⚙️ Click **Settings**

---

### 7.3 🔐 Change Secure Boot Template

1. In the left panel, select **Security**
2. Ensure:

   * ☑️ **Enable Secure Boot** (checked)
3. Change **Template**:

   * ❌ `Microsoft Windows`
   * ✅ **Microsoft UEFI Certificate Authority**

⚠️ **Do NOT disable Secure Boot**
Only change the template.

4. ✅ Click **Apply**
5. ✅ Click **OK**

---

## 8️⃣ Start the VM Again

1. 🖱️ Right-click **Ubuntu**
2. 🔌 Click **Connect**
3. ▶️ Click **Start**

---
