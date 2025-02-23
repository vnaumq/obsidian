[[Practice]]

### **What is port forwarding?**

Port forwarding is **redirecting incoming connections** from the host (MacBook) to the virtual machine.

Example:  
Let’s say MacBook’s port `22` is already in use, but `2222` is free.  
We configure port forwarding so that:

- **MacBook (127.0.0.1:2222) → VM (10.0.2.15:22)**

Now, you can connect using:

bash

CopyEdit

`ssh -p 2222 vnaumq@127.0.0.1`

MacBook will forward the request to port `22` inside the VM.