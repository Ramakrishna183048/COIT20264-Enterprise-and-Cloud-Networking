# Week 8 – Azure Resource Management and Microsoft Entra

## Portfolio Task 1 – Manage Azure Resource Groups

In this task, I used the Azure Portal to explore resource groups, view existing resources, create a new resource, and examine the management options available for an Azure resource.

### Step 1 – View Resources in a Resource Group

I opened the existing resource group `RG1-lod64885057` and viewed the resources available inside it. The resource group contained six resources, including a virtual network, storage accounts, a virtual machine, a network interface and a public IP address.

![Resources in RG1](images/week8-task1-resource-RG1.png)

*Figure 1: Resources available in the RG1 resource group.*

### Step 2 – Create a Resource in a Resource Group

I worked with the `RG2-lod64885057` resource group and created the storage account `mystorage64885057`. The storage account was successfully deployed and its provisioning state showed `Succeeded`.

![Storage Account in RG2](images/week8-task1-RG2-resource-overview.png)

*Figure 2: Storage account successfully created in the RG2 resource group.*

### Step 3 – View Resource Management Options

I opened the storage account and explored the available management options in the Azure Portal. The resource menu provided options such as Activity log, Access Control (IAM), Data migration, Storage browser, Networking, Access keys, Shared access signature and Encryption.

![Storage Account Management Options](images/week8-task1-overview.png)

*Figure 3: Management options available for the Azure storage account.*

---

## Task 2 – Manage Microsoft Entra Users and Groups

In this task, I completed the **AZ900-013: Manage Microsoft Entra Users and Groups** guided lab. The activity helped me understand how Microsoft Entra ID can be used to manage a tenant, users, groups, and user access.

### Modify the Microsoft Entra Tenant

First, I opened the Microsoft Entra ID tenant and modified the **Technical contact** in the tenant properties. After saving the change, I used the lab verification to confirm that the technical contact was updated successfully.

### Create a Microsoft Entra User

I created a new Microsoft Entra user named **Riley Burgess**. I configured the user account with the required user principal name and user information provided in the lab.

The lab verification confirmed that the Riley Burgess user account was created successfully.

### Create a Microsoft Entra Group

Next, I created a security group named **MyGroup** with the membership type set to **Assigned**.

I added **Riley Burgess** as a member of MyGroup. The lab verification confirmed both the creation of the group and the addition of Riley Burgess as a member.

### Initial Sign-In and Password Change

I then signed in using the **Riley Burgess** Microsoft Entra account in an InPrivate browser window. During the initial sign-in process, the user's initial password was changed to a new password as required by the lab.

After the password change, the account successfully proceeded to the Microsoft authentication setup stage.

### Lab Completion

The final lab result showed **100% completion**. All four activities were successfully completed:

- Modify a Microsoft Entra tenant
- Create a Microsoft Entra user
- Create a Microsoft Entra group
- Change a user's password during initial sign-in

![AZ900-013 Lab Completed](images/week8-task2-az900-013-completed-100.png)

*Figure: AZ900-013 Manage Microsoft Entra Users and Groups guided lab completed with 100%.*

### What I Learned

- I learned how Microsoft Entra ID is used to manage users and identities in a cloud environment.
- I learned how to create a new Microsoft Entra user account.
- I created a security group and added a user as a member of the group.
- I learned how tenant information, such as the technical contact, can be updated.
- I learned how a user's password is changed during the initial sign-in process.
- This activity helped me understand how Microsoft Entra ID can be used to manage users, groups and access in Azure.
