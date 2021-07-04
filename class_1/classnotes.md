Interface: A device or system where entities like packets interact with each other. i.e. NIC: Network Interface Card delivers packets from hardware to kernel.
Kernel space: Kernel space is where the kernel aka the operating system executes and provides its services. Kernel manages resources of the operating system.
User space: Everything other than the kernel is a user process and user space is where all the user processes run. Not to mention that when a program is executing it's known as a process. User space requests to kernel space for it's required hardware services via systemcall(i.e. syscall).
DHCP: Dynamic Host Control Protocol.
CIDR: Classless Inter-Domain Routing. An IP addressing system that helps in the allocation of IP addresses. i.e.:172.17.0.0/16
Gateway:Just a node in a computer network or more like a stoppage point for data when it comes from another network or is going to one.
CAM Table: Content Addresable Memory Table. It stores info about MAC addresses available on physical ports with their associated vlan parameters.
| MAC addresses | Port          | vlan  |
| ------------- |:-------------:| -----:|
| 0000.0000.1111|        3      |    1  |
| 0000.0000.2222|        2      |    2  |
| 0000.0000.3333|        1      |    3  |

**packets usually have the payload (the data), the source IP and the destination IP**
Cloud: The concept of virtualization of a greater physical resource into smaller ones is called Cloud. Cloud includes firewall. 
| FAT server | ->Switch | ->Router |->firewall |
Hypervisor: Does the work of cutting the greater resource into smaller ones in the cloud.
SDN: Software Defined Network.
SDS: Software Defined Storage.
**Docker is nothing but a process,Self contained process,thus a container**
*Since docker is a process it runs on a OS, that means to run docker you need to VM*
***Since docker is a container, it can overcome the restrictions of VM (i.e.: containing 3 different version of nodejs at a time)***
Docker daemon: basically a for loop which is running inside the docker container.
namespace: a feature of linux-kernel...a privacy locked feature...which is idea behind docker container.
| Docker container |<-run->| Docker image |<-build->| Dockerfile |
**Dockerimage is nothing but a .zip file**
