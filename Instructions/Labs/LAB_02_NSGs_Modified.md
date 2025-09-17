lab:
    title: '02 - Network Security Groups and Application Security Groups'
    module: 'Module 01 - Plan and implement security for virtual networks'
---

# Lab 02: Network Security Groups and Application Security Groups
# Student lab manual

## Lab scenario

You have been asked to implement your organization's virtual networking infrastructure and test to ensure it is working correctly. In particular:

- The organization has two groups of servers: Web Servers and Management Servers.
- Each group of servers should be in its own Application Security Group. 
- You should be able to RDP into the Management Servers, but not the Web Servers.
- The Web Servers should display the IIS web page when accessed from the internet. 
- Network security group rules should be used to control network access. 

> For all the resources in this lab, we are using the **East US** region. Verify with your instructor this is the region to use for class. 

## Lab objectives

In this lab, you will complete the following exercises:

- Exercise 1: Create the virtual networking infrastructure
- Exercise 2: Deploy virtual machines and test the network filters

## Network and Application Security Groups diagram

![Diagram showing the process flow of the lab tasks.](../media/network-and-application-security-groups-diagram.png)

## Instructions

### Exercise 1: Create the virtual networking infrastructure

### Estimated timing: 20 minutes

In this exercise, you will complete the following tasks:

- Task 1: Create a virtual network with one subnet.
- Task 2: Create two application security groups.
- Task 3: Create a network security group and associate it with the virtual network subnet.
- Task 4: Create inbound NSG security rules to all traffic to web servers and RDP to the management servers.

#### Task 1:  Create a virtual network

1. Sign-in to the Azure portal **`https://portal.azure.com/`**.

    >**Note**: Sign in to the Azure portal using your assigned student account.

2. In the Azure portal, in the **Search resources, services, and docs** text box at the top of the Azure portal page, type +++Virtual networks+++ and press the **Enter** key.

3. On the **Virtual networks** blade, click **+ Create**.

4. On the **Basics** tab of the **Create virtual network** blade, specify the following settings (leave others with their default values) and click **Next: IP Addresses**:

    |Setting|Value|
    |---|---|
    |Subscription | Name of the Azure subscription you are using in this lab |
    |Resource group | **AzSecLab02-XX** (replace **XX** with your student ID number, e.g., `AzSecLab02-05`) |
    |Name| +++myVirtualNetwork+++ |
    |Region| **East US** |

...

#### Task 2:  Create application security groups

|Setting|Value|
|---|---|
| Resource group | **AzSecLab02-XX** |
| Name | +++myAsgWebServers+++ |
| Region | **East US** |

(… 동일하게 myAsgMgmtServers 생성 시도에서도 Resource group → **AzSecLab02-XX**)

...

#### Task 3:  Create a network security group and associate the NSG to the subnet

|Setting|Value|
|---|---|
| Resource group | **AzSecLab02-XX** |
| Name | +++myNsg+++ |
| Region | **East US** |

...

### Exercise 2: Deploy virtual machines and test network filters

|Setting|Value|
|---|---|
|Resource group|**AzSecLab02-XX**|
|Virtual machine name|**myVmWeb**|

(… 동일하게 myVMMgmt VM 생성 시 Resource group → **AzSecLab02-XX**)

...

**Clean up resources**

```powershell
Remove-AzResourceGroup -Name "AzSecLab02-XX" -Force -AsJob
```

> Replace **XX** with your student ID number.
