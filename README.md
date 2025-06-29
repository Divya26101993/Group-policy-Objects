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

In Theory:

Computer Configuration contains settings that apply to computers regardless of who logs on, managing system-wide policies and preferences

User Configuration contains settings that apply to users regardless of the computer they log on to, managing user-specific policies and preferences

Policies are mandatory settings enforced by the system that users cannot override.

Preferences are optional settings that can be preconfigured but allow users to make changes

We have configured the above settings in accordance with our Group Policy Objects (GPOs)

![Image](https://github.com/user-attachments/assets/835f98c3-d4ac-4390-a576-7a8980009c63)

By expanding the Policies and Preferences sections, you’ll find additional settings. This is where you can configure and apply policies and preferences based on your specific requirements

![Image](https://github.com/user-attachments/assets/ed4fa486-43d0-446c-ae01-2702793df2b6)

### Step 2: Creating a Password Policy

In this step, we will configure a password policy to enforce security settings such as password complexity, length, and expiration

In GPMC, right-click on IT.local and select Create a GPO in this domain, and Link it here…

![Image](https://github.com/user-attachments/assets/544ccd44-486d-447e-a6b5-8bb6d073d49b)

The New GPO dialog box will appear

![Image](https://github.com/user-attachments/assets/9ae9f2f1-c932-4ad9-be66-0df1670b5d8c)

Next, rename the GPO to Password Policy to clearly reflect its purpose and keep it straightforward

![Image](https://github.com/user-attachments/assets/3512eff6-20d0-4e98-bf8a-97bc6fab6b20)

You will now see the new GPO named Password Policy listed under Group Policy Objects

![Image](https://github.com/user-attachments/assets/8869ad76-4df8-4c59-9e61-33a03e9d410c)

To change or edit a policy setting, right-click the setting and select Edit

![Image](https://github.com/user-attachments/assets/a24b72b0-e6df-45ae-b503-e1b6c805e56c)

As mentioned earlier, the User Configuration and Computer Configuration sections will appear. In this case, we are selecting Computer Configuration because we are applying a password policy at the computer level. This ensures that the policy cannot be changed or modified by the user

Navigation Path:

Computer Configuration -> Policies -> Windows Settings ->Security Settings -> Account Policies -> Password Policy

![Image](https://github.com/user-attachments/assets/9f0ab2d4-4b3a-47f4-ad36-fb151c38f698)

On the right-hand side, you will see a list of policies and their corresponding settings. Select the relevant policies from the list and enable them as needed

![Image](https://github.com/user-attachments/assets/df90173c-8a33-4723-9aad-3f92bba9f108)

First, select Minimum Password Length and double-click on it to open the settings

![Image](https://github.com/user-attachments/assets/9f856abe-81b0-4f2f-99db-10432a37e812)

The following settings window will open

![Image](https://github.com/user-attachments/assets/f89bd470-6ae2-4d56-859b-53c3c14d3777)

In the settings window, check Define this policy setting, and set the minimum password length to 12 characters.

![Image](https://github.com/user-attachments/assets/5249400c-7992-4c50-aab0-53b922be5c0a)

The configured setting will now be visible in the Group Policy Management Editor (GPM Editor)

![Image](https://github.com/user-attachments/assets/417e1ac5-b44e-4bf0-85a0-3ebfb99eb9e7)

When you double-click the Password must meet complexity requirements policy, the settings window will open

![Image](https://github.com/user-attachments/assets/d994f0e7-55cc-4e0f-aba7-178a20ef7d2d)


