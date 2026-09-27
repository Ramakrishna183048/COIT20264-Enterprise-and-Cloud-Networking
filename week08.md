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

## Portfolio Task 2 – Manage Microsoft Entra Users and Groups

### 1. Create a Microsoft Entra User

I created a new Microsoft Entra user named **Riley Burgess**. The user was created as a member of the Microsoft Entra tenant.

![Riley Burgess User Created](images/week8-task2-riley-user-created.png)

*Figure 4: Microsoft Entra user Riley Burgess successfully created.*

### 2. Create a Microsoft Entra Group

I created a Microsoft Entra group named **MyGroup** and added **Riley Burgess** as a member. The lab verification confirmed that the group was created and Riley Burgess was successfully added to it.

![MyGroup with Riley Burgess](images/week8-task2-mygroup-riley-completed.png)

*Figure 5: MyGroup successfully created with Riley Burgess added as a member.*

### 3. Initial Sign-In and Password Change

I signed in to Azure using the Riley Burgess account and completed the initial password change process. The lab verification confirmed that the sign-in and password change were completed successfully.

![Riley Password Change](images/week8-task2-riley-password-change-verified.png)

*Figure 6: Initial sign-in and password change successfully completed for Riley Burgess.*

### 4. Lab Completion

The AZ900-013 guided lab was successfully completed with a final result of **100%**. The completed activities included modifying the Microsoft Entra tenant, creating a Microsoft Entra user, creating a Microsoft Entra group, and completing the user's initial sign-in and password change.

![AZ900-013 Completed](images/week8-task2-az900-013-completed-100.png)

*Figure 7: AZ900-013 Manage Microsoft Entra Users and Groups guided lab completed with 100%.*

### Discussion – Users and Groups for an Application Scenario

For an application, separate user accounts can be created for people who need access to the system. Users with similar responsibilities can then be organised into groups. For example, groups could be created for administrators, staff and normal users. This makes access management easier because permissions can be managed through groups instead of separately for every user.

### What I Learned

- I learned how Microsoft Entra ID can be used to manage users and groups.
- I learned how to create a new Microsoft Entra user.
- I learned how to create a security group and add a user to the group.
- I learned how to complete the initial sign-in and password change process for a new user.
- I understood how groups can make identity and access management easier when managing multiple users.
