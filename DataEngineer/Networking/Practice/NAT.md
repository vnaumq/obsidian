[[Practice]]

### **NAT (Network Address Translation) – Address translation mechanism**

NAT allows devices inside a local network **to use a single external IP address** for communication with the internet.

### **How does NAT work in VirtualBox?**

- The virtual machine (VM) gets an **internal IP** (e.g., `10.0.2.15`).
- The outside world (including your MacBook) **cannot see this IP**.
- However, the VM **can access the internet** via the **host machine's IP (MacBook).**

### **The problem with NAT – No direct access to the VM**

Since NAT hides the VM behind the host, it is **not accessible directly**.  
This is where **port forwarding** comes in.