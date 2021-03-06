# Difference between Containers and Virtual Machines

Before diving into text lets look at the component view of how virtual machines and containers are implemented.

![Component View](https://github.com/collabnix/dockerlabs/blob/master/beginners/images/difference-vm-containers.png)

## Virtual Machine

If look at how virtual machines are built over the physical hardware, There is a layer of Hypervisor which sits between physical hardware and operating systems.
In a broad view hypervisor is used to virtualize the hardware which is then configured with the way a user wants it to.

Thus, While using virtual machines our physical machine is divided into parts.

**Example:**
Say, I have a server with 8GB RAM, I create two virtual machines each with 4GB RAM. Now, what happened is I divided my server into two parts each with 4GB RAM and would never be able to use that underlying 8GB RAM altogether again, Only access I have will be that 2 4GB RAM machines. 

## Containers

Unlike virtual machines where hypervisor divides physical hardware into parts, Containers are like normal operating system processes. Now the question is, if containers are like normal processes then how come there are isolated from other processes. This is where namespaces come into picture.

Namespaces is an advance concept in linux where each namespace has its own isolated resources without actual partitioning of the underlying hardware. Namesapces are used to virtualize the underlying operating system.

Since containers are nothing other than OS processes, This is the reason why lifting a container takes seconds and lifting a virtual machine takes minutes.

## Conclusion

Prime differnce between Containers and Virtual Machine is the virtualization of *Operating System* and *Hardware* respectively. While using Virtual machine each virtual machine has its own underlying operating system whereas, While using containers, Each container runs on same underlying operating system instance, While underlying OS is the same containers can still have different OS environment in their respective namespace.

## References

* https://blog.netapp.com/blogs/containers-vs-vms/
* https://www.toptal.com/linux/separation-anxiety-isolating-your-system-with-linux-namespaces 