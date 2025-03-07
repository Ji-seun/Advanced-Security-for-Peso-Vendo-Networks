# BOS TAURUS AI GUARD SYSTEM  

🚀 **BOS TAURUS AI GUARD SYSTEM** is a security solution designed to block unauthorized access to **Starlink Admin (192.168.100.1)** from **Peso Vendo (Ether3) users** and redirect them to a custom warning page.  

## 🎯 Features  
✅ **Blocks unauthorized access** to `192.168.100.1` from **Ether3 (Peso Vendo)**.  
✅ **Redirects users** to a warning page (your static website) .  
✅ **Enhances security** by preventing unauthorized users from modifying Starlink settings.  
✅ **Lightweight and fast**, hosted on a simple static HTML page.  

---

## 🛠️ Setup Guide  

### **1️⃣ Upload the Custom HTML Page**  
1. Host the **`index.html`** file on a **static web server** or GitHub Pages.  
2. Ensure your custom page URL (your static website) is accessible.  

### **2️⃣ Configure MikroTik to Block & Redirect**  
Run the following script in **MikroTik Terminal**:  

```sh
# ✅ Enable Web Proxy
/ip proxy set enabled=yes port=8080

# ✅ Block direct access to Starlink Admin Page from Ether3 (Peso Vendo)
/ip firewall filter add chain=forward src-address=192.168.2.0/24 dst-address=192.168.100.1 action=reject reject-with=icmp-host-unreachable comment="BOS TAURUS AI GUARD SYSTEM - Blocking Unauthorized Starlink Access"

# ✅ Redirect Unauthorized Users to BOS TAURUS AI GUARD SYSTEM Page
/ip firewall nat add chain=dstnat src-address=192.168.2.0/24 dst-address=192.168.100.
