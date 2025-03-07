BOS TAURUS AI GUARD SYSTEM 🚀🔒
Advanced Security for Peso Vendo Networks

📌 Overview
The BOS TAURUS AI GUARD SYSTEM is a MikroTik-based security solution designed to block unauthorized access to the Starlink Admin Panel (192.168.100.1) from Ether3 (Peso Vendo Network) and redirect users to a custom warning page.

🔒 Prevents unauthorized users from rebooting or modifying Starlink settings.
🌍 Redirects blocked users to BOS TAURUS AI GUARD SYSTEM Page.
⚡ Enhances security without affecting internet access.

🛠 MikroTik Configuration (Terminal Commands)
Run the following script in the MikroTik Terminal to enable security features:

# ✅ Enable Web Proxy
/ip proxy set enabled=yes port=8080

# ✅ Block direct access to Starlink Admin Page from Ether3 (Peso Vendo)
/ip firewall filter add chain=forward src-address=192.168.2.0/24 dst-address=192.168.100.1 action=drop comment="BOS TAURUS AI GUARD SYSTEM - Blocking Unauthorized Starlink Access"

# ✅ Redirect Unauthorized Users to BOS TAURUS AI GUARD SYSTEM Page
/ip firewall nat add chain=dstnat protocol=tcp dst-address=192.168.100.1 dst-port=80,443 action=dst-nat to-addresses=YOUR_MIKROTIK_IP to-ports=8080 comment="Redirect Unauthorized Starlink Access to Web Proxy"

/ip proxy access add dst-host=192.168.100.1 redirect-to=https://ji-seun.github.io/bostaurusAIGuardSystem/ action=deny comment="BOS TAURUS AI GUARD SYSTEM - Redirect to Custom Page"
📌 Features
✅ Blocks unauthorized access to 192.168.100.1 (Starlink Admin) from Peso Vendo users.
✅ Prevents network abuse (reboots, stow attempts, or hacking).
✅ Redirects unauthorized users to a custom security warning page.
✅ Ensures Starlink admin access is only available to trusted users.

🖥️ How It Works
A Peso Vendo user tries to access 192.168.100.1.
BOS TAURUS AI GUARD SYSTEM blocks the request.
The user is redirected to BOS TAURUS AI GUARD SYSTEM Page.
No access to Starlink Admin Panel!
⚡ Next Steps
Run the script in MikroTik Terminal.
Test by accessing 192.168.100.1 from a Peso Vendo connection.
If successful, users will see the BOS TAURUS AI GUARD SYSTEM warning page.
📌 For improvements, updates, and troubleshooting, visit the GitHub repository.

📢 License
This project is open-source and free to use.
Developed by BOS TAURUS AI GUARD SYSTEM Team.

🚀 Stay Secure. Stay Protected.


/ip firewall filter add chain=forward src-address=192.168.2.0/24 dst-address=192.168.100.1 action=reject reject-with=icmp-host-unreachable comment="BOS TAURUS AI GUARD SYSTEM - Blocking Unauthorized Starlink Access"

# ✅ Redirect Unauthorized Users to BOS TAURUS AI GUARD SYSTEM Page
/ip firewall nat add chain=dstnat src-address=192.168.2.0/24 dst-address=192.168.100.
