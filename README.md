## Group-policy-Objects

A step-by-step guide on how to create Group Policies in Group Policy Manangement Console (GPMC)

## Prerequisites

1. Windows server installation: Install Windows server on a virtual machine
2. Active Directory Domain Services (AD DS): Install and configure AD DS to create a Domain
3. Group Policy Management Console (GPMC): Install GPMC on your Windows Server to manage GPOs

## Installation Steps

### Step 1: Creating Group Policies in Group Policy management console

The virtual machine is set up with Windows Server 2022, and both Active Directory Domain Services (AD DS) and Group Policy Management Console (GPMC) have been successfully installed and configured

Open Group Policy Management Console (GPMC):
Type “Group Policy Management” in the Windows search box or
Start > Windows Administrative Tools > Group Policy Management

![Image](https://github.com/user-attachments/assets/d5b6d7b4-bfcf-486e-b899-d72a47591e48)

![Image](https://github.com/user-attachments/assets/ea49c7a0-c109-4e04-a44c-1babfcb56243)

In a previous repository, I created an Active Directory domain named IT.local, as shown in the screenshot below

![Image](https://github.com/user-attachments/assets/558941b9-d27e-421a-9a2b-fa6cf73fc2a4)

Now, refer to the images below to see how to locate the existing Default Domain Controllers Policy and how to edit it

In the left panel, expand:
Forest:IT.local-> Domains-> IT.local-> Group Policy Objects-> Default Domain controller Policy

![Image](https://github.com/user-attachments/assets/62176a9d-f3db-4720-a94e-d85d2eac4b89)

![Image](https://github.com/user-attachments/assets/911bb002-45f4-4634-b68d-fa52cbb2e45d)

![Image](https://github.com/user-attachments/assets/d3743c79-4c57-46c1-82e7-d4808d1ebaaf)

![Image](https://github.com/user-attachments/assets/62990551-2b36-4e60-8981-db606e9c540f)

To modify the policy settings, right-click on Default Domain Controllers Policy and select Edit

![Image](https://github.com/user-attachments/assets/fad507fe-92b3-4365-982c-543bf8d1c433)

On the next screen, you'll see Computer Configuration and User Configuration, each containing Policies and Preferences sections

![Image](https://github.com/user-attachments/assets/835f98c3-d4ac-4390-a576-7a8980009c63)

If you expand
