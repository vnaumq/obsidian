[[Practice]]

## **What is Bridge Adapter and why doesn’t it need port forwarding?**

### **Bridge Adapter – Direct integration of the VM into the local network**

With **Bridge Adapter**, the VM **gets an IP address from the router** and becomes a **regular network device**.

#### **How does it work?**

- The VM gets an IP address **in the same network as the MacBook** (e.g., `192.168.1.100`).
- It is **visible to other devices** in the network.
- You can **connect to it directly** without port forwarding:
    
    `ssh vnaumq@192.168.1.100`
    

### **Why doesn’t Bridge Adapter require port forwarding?**

Because the VM **already has a real IP address** that other devices can reach.  
Port forwarding is only needed with **NAT**, where the VM has no direct IP.

