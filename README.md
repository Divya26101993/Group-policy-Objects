## Group-policy-Objects

A Step-by-Step Guide to Creating **Group Policies** in the **Group Policy Management Console (GPMC)**

## Introduction

GPO (Group Policy Object): A collection of settings that can be applied to computers or users in a domain to manage system behavior.

GPMC (Group Policy Management Console): A Microsoft management tool used to create and manage GPOs.

AD DS (Active Directory Domain Services): The directory service in Windows Server that stores data about users, computers, and other objects in a network.

## Prerequisites

1. Windows server installation: Install Windows server on a virtual machine
2. Active Directory Domain Services (AD DS): Install and configure AD DS to create a Domain
3. Group Policy Management Console (GPMC): Install GPMC on your Windows Server to manage GPOs

## Installation Steps

### Step 1: Creating a New GPO and Editing It

We have set up a virtual machine running Windows Server 2022 with Active Directory Domain Services (AD DS) and the Group Policy Management Console (GPMC) installed and configured.

Open Group Policy Management Console (GPMC):
Type **Group Policy Management** in the Windows search box or
**Start -> Windows Administrative Tools -> Group Policy Management**

![Image](https://github.com/user-attachments/assets/d5b6d7b4-bfcf-486e-b899-d72a47591e48)

![Image](https://github.com/user-attachments/assets/ea49c7a0-c109-4e04-a44c-1babfcb56243)

In this setup, an Active Directory domain named **IT.local** has already been created. Refer to the screenshot below for confirmation

![Image](https://github.com/user-attachments/assets/558941b9-d27e-421a-9a2b-fa6cf73fc2a4)

Now, refer to the images below to see how to locate the existing Default Domain Controllers Policy and how to edit it

In the left panel, expand:

**Forest: IT.local -> Domains -> IT.local -> Group Policy Objects -> Default Domain controller Policy**

![Image](https://github.com/user-attachments/assets/62176a9d-f3db-4720-a94e-d85d2eac4b89)

![Image](https://github.com/user-attachments/assets/911bb002-45f4-4634-b68d-fa52cbb2e45d)

![Image](https://github.com/user-attachments/assets/d3743c79-4c57-46c1-82e7-d4808d1ebaaf)

![Image](https://github.com/user-attachments/assets/62990551-2b36-4e60-8981-db606e9c540f)

To modify the policy settings, **right-click** on **Default Domain Controllers Policy** and select **Edit**

![Image](https://github.com/user-attachments/assets/fad507fe-92b3-4365-982c-543bf8d1c433)

On the next screen, you'll see Computer Configuration and User Configuration, each containing Policies and Preferences sections

In Theory:

**Computer Configuration** contains settings that apply to computers regardless of who logs on, managing system-wide policies and preferences

**User Configuration** contains settings that apply to users regardless of the computer they log on to, managing user-specific policies and preferences

**Policies** are mandatory settings enforced by the system that users cannot override.

**Preferences** are optional settings that can be preconfigured but allow users to make changes

We have configured the above settings in accordance with our Group Policy Objects (GPOs)

![Image](https://github.com/user-attachments/assets/835f98c3-d4ac-4390-a576-7a8980009c63)

By expanding the Policies and Preferences sections, you’ll find additional settings. This is where you can configure and apply policies and preferences based on your specific requirements

![Image](https://github.com/user-attachments/assets/ed4fa486-43d0-446c-ae01-2702793df2b6)

### Step 2: Creating a Password Policy

In this step, we will configure a **password policy** to enforce security settings such as password complexity, length, and expiration

In the **Group Policy Management Console (GPMC)**, right-click on **IT.local**, select **Create a GPO in this domain, Link it here**..

![Image](https://github.com/user-attachments/assets/544ccd44-486d-447e-a6b5-8bb6d073d49b)

The **New GPO dialog box** will appear

![Image](https://github.com/user-attachments/assets/9ae9f2f1-c932-4ad9-be66-0df1670b5d8c)

Next, rename the GPO to **Password Policy** to clearly reflect its purpose and keep it straightforward

![Image](https://github.com/user-attachments/assets/3512eff6-20d0-4e98-bf8a-97bc6fab6b20)

You will now see the new GPO named Password Policy listed under Group Policy Objects

![Image](https://github.com/user-attachments/assets/8869ad76-4df8-4c59-9e61-33a03e9d410c)

To change or **edit a policy setting**, right-click the setting and select **Edit**

![Image](https://github.com/user-attachments/assets/a24b72b0-e6df-45ae-b503-e1b6c805e56c)

As mentioned earlier, the User Configuration and Computer Configuration sections will appear. In this case, we are selecting Computer Configuration because we are applying a password policy at the computer level. This ensures that the policy cannot be changed or modified by the user

Navigation Path:

**Computer Configuration -> Policies -> Windows Settings -> Security Settings -> Account Policies -> Password Policy**

![Image](https://github.com/user-attachments/assets/9f0ab2d4-4b3a-47f4-ad36-fb151c38f698)

On the right-hand side, you will see a list of policies and their corresponding settings. Select the relevant policies from the list and enable them as needed

![Image](https://github.com/user-attachments/assets/df90173c-8a33-4723-9aad-3f92bba9f108)

First, select **Minimum Password Length** and double-click on it to open the settings

![Image](https://github.com/user-attachments/assets/9f856abe-81b0-4f2f-99db-10432a37e812)

The following settings window will open

![Image](https://github.com/user-attachments/assets/f89bd470-6ae2-4d56-859b-53c3c14d3777)

In the Password Policy Settings window, Tick **Define this policy setting** and set the **minimum password** length to 12 characters.

![Image](https://github.com/user-attachments/assets/5249400c-7992-4c50-aab0-53b922be5c0a)

The configured setting will now be visible in the **Group Policy Management Editor (GPM Editor)**

![Image](https://github.com/user-attachments/assets/417e1ac5-b44e-4bf0-85a0-3ebfb99eb9e7)

When you double-click the Password must meet complexity requirements policy, the settings window will open

![Image](https://github.com/user-attachments/assets/d994f0e7-55cc-4e0f-aba7-178a20ef7d2d)

On the same screen where you click 'Explain,' the minimum password requirements are also displayed

![Image](https://github.com/user-attachments/assets/624e9bd8-35f4-4de7-970f-399f7b43ff79)

We're updating the password age policy, meaning you will be required to change your password after a set period (e.g., every 90 days)

![Image](https://github.com/user-attachments/assets/6db63113-f8b0-4507-bbf2-23232258fae6)

![Image](https://github.com/user-attachments/assets/1423d1f7-9128-4dc3-b11b-0bbdb342a934)

When you update the password expiration period to 90 days, the screen below will appear, showing the default or suggested setting (30 days). Once updated, click **OK** to confirm the change to 90 days

![Image](https://github.com/user-attachments/assets/1554569c-0144-4478-8a2f-02037809b675)

There are several other options available for customization. I've modified a few additional settings based on the company's policy, and these adjustments have been implemented accordingly.

![Image](https://github.com/user-attachments/assets/f1cebcc0-d9e7-42e9-9b38-6678d7189e51)

Once all changes are made, if you need to make any further adjustments, right-click on the policy (Password Policy) and select **Edit**.You can modify the settings whenever necessary

![Image](https://github.com/user-attachments/assets/a92f056e-ace3-4cc6-8e9b-6504e45c8bfe)

![Image](https://github.com/user-attachments/assets/22a1f973-7728-4cbc-8509-f3731f2d6887)

### Step 3:  Creating Drive Mapping Policy

As mentioned earlier, right-click on **IT.local** and select **Create GPO**. Name it **Drive Mapping**

![Image](https://github.com/user-attachments/assets/6f9f86de-e07e-417f-b747-0ac10a14695a)

Now, the Drive Mapping GPO will appear under IT.local

![Image](https://github.com/user-attachments/assets/42d42a4b-176c-45b5-a5c2-babcbf4b496a)

Next, right-click on **Drive Mapping** and select **Edit**. The screen below will open

![Image](https://github.com/user-attachments/assets/5edd7e8e-ede9-4cf5-bcd9-f8243dd66a55)

This GPO falls under User Configuration because it applies to the user, who is the one utilizing this policy. Select Preferences since the user can modify or change the drive whenever necessary

**Navigation path: User configuration -> Preferences -> Windows settings -> Drive Maps -> Right click -> New -> Mapped drive**

![Image](https://github.com/user-attachments/assets/7aae73b7-2ec8-4858-938a-d2f3c7051211)

![Image](https://github.com/user-attachments/assets/dfd5499e-95aa-4a16-af6b-d665afc37459)

In the screen below, you can specify the path of the network share and select the drive letter as shown in the images below and click **Apply** and **Ok**

![Image](https://github.com/user-attachments/assets/9f2b8e6b-a65e-4c93-ad1f-99edcd22d34f)

![Image](https://github.com/user-attachments/assets/21f325b1-30e9-4371-8382-24319b2ab496)

You should now see the network drive and its path listed under Drive Mapss

### Step 4:Creating Desktop Wallpaper Policy

In this **Desktop Wallpaper Policy**, we've configured a default wallpaper for all users.

The process of creating a new GPO is the same for all policies

In the screen below, you can see that I've already created a GPO called **Desktop Wallpaper Policy** under **IT.local**

![Image](https://github.com/user-attachments/assets/db898209-cd3a-40c1-a273-49f7b190e10a)

This policy is applied to users, so we need to select User Configuration

**Navigation Path: User configuration -> Administrative templates:Policy definitions -> Desktop**

![Image](https://github.com/user-attachments/assets/d15623fa-5574-4851-afc9-0b758d203eea)

When you click on Desktop, you'll see many options related to desktop changes. From the list, **select Desktop Wallpaper**

![Image](https://github.com/user-attachments/assets/9de9c930-89c6-4ff2-805f-230e38f4d0c9)

Now, the screen below will open. In this, we enable the policy, then under **Wallpaper Name**, select the **path to the wallpaper**. For **Wallpaper Type**, we typically choose **Fill or Center**

![Image](https://github.com/user-attachments/assets/e6312af9-de02-4ec7-9e85-9aece92cfa27)

![Image](https://github.com/user-attachments/assets/be85755a-3ba6-41a5-80e2-c3c468dd7c63)

### Step 5: Creating Policy to  Restrict Access to control Panel

In this policy, we are preventing users from accessing the Control Panel

Follow the same steps to create and edit the policy

In the **Group Policy Management Editor (GPM)**, select **User Configuration** because this policy applies to users

**Navigation Path: User Configuration -> Policies -> Administrative templates -> control panel**

![Image](https://github.com/user-attachments/assets/530df254-6297-4d7d-92da-f351ef07ee3e)

Similar to other GPOs, this one also offers many options. We choose **Prohibit access to Control Panel and PC settings**

![Image](https://github.com/user-attachments/assets/8479de87-6454-4026-bd1f-4d4186d1975e)

When you click on it, the screen below will open. Select **Enabled**, then click **Apply** and **OK**

![Image](https://github.com/user-attachments/assets/f77e195a-23ee-4ce5-9193-d74bdf8e286d)

![Image](https://github.com/user-attachments/assets/21c02bff-550c-4e5b-92b4-c5fd10dfead7)

![Image](https://github.com/user-attachments/assets/d033537b-dad3-4d71-a5fd-7f997566b813)

### Step 6: Creating policy to Disable USB storage

In this policy, we are preventing users from using USB storage devices

This policy is useful in environments where data security is critical, and USB storage devices need to be disabled to prevent data leaks or malware infections.

Create a new GPO called **Disable USB Storage**, right-click on it, and select **Edit**

![Image](https://github.com/user-attachments/assets/cbceee61-cff8-458d-bad8-f0eced279ec0)

![Image](https://github.com/user-attachments/assets/8f4875ad-2a62-46ae-a48b-c0fd5cc04605)

In the GPM Editor, this policy is applied under Computer Configuration because it directly affects the computer. This will prohibit any user from using a USB storage device on the computer

**Navigation path: Computer Configuration -> Policies -> Administrative templates -> System -> Removable storage devices**

![Image](https://github.com/user-attachments/assets/7c35233d-9fad-45a7-af50-4f9111de4a9e)

On the right-hand side, select **All Removable Storage Classes: Deny all access**

![Image](https://github.com/user-attachments/assets/ec33a005-a7ed-4fb0-b842-1c6571d34c32)

In the next screen, select **Enabled**, then click **Apply** and **OK**

![Image](https://github.com/user-attachments/assets/3fcd9294-f69f-496c-86ce-ab240bd8673a)

![Image](https://github.com/user-attachments/assets/e74b2ef2-f5fa-4555-82c0-689b5bc6d16f)

![Image](https://github.com/user-attachments/assets/f201f55e-89f2-48cf-ab5c-f879348d3a76)

### Step 7:  Creating Account lockout Policy

This policy is set to prevent brute force attacks

First, create a **New GPO** called **Account Lockout Policy**, right-click on it, and select **Edit**

![Image](https://github.com/user-attachments/assets/5db7c1f2-8205-449f-a3bb-d485bba7294b)

![Image](https://github.com/user-attachments/assets/b74b8547-87ec-4971-802e-c4362e163865)

This policy is implemented under Computer Configuration and applies to all computers within the domain, preventing unauthorized login attempts by locking the account after multiple failed login attempts

**Navigation Path: Computer Configuration -> Policies -> Windows settings -> Security settings -> Account policies**

![Image](https://github.com/user-attachments/assets/4ef6977e-c524-4d23-80b7-a0278d3f12a4)

On the right-hand side, select **Account Lockout Policy**

![Image](https://github.com/user-attachments/assets/a9570262-6bf1-4560-b617-a5c5fce92b04)

On the next screen, you can select **Account Lockout Duration**

![Image](https://github.com/user-attachments/assets/1b53e046-7bcd-454e-8e03-7e868cb10b10)

The next screen will prompt you to specify how long the system should remain locked out after a certain number of failed attempts

Tick **Define this policy setting**, then enter the number of minutes for the lockout duration. Click **Apply** and it will show Account Lockout Threshold, which determines the number of failed attempts before the account is locked,. Then Click **Ok**

![Image](https://github.com/user-attachments/assets/cf55f0b2-bb6f-483f-9b6f-48de91a150d1)

![Image](https://github.com/user-attachments/assets/9625a7cc-19e7-47f6-8214-e37defa0b98e)

![Image](https://github.com/user-attachments/assets/1e889d15-6a07-499b-a2ac-cc35d8e72510)

The final screen will display the list of all policies created under **IT.local**

![Image](https://github.com/user-attachments/assets/7a417933-d8d6-4539-bcd9-6081b2738d84)

## Conclusion

Congratulations! You’ve successfully created and configured several Group Policy Objects. Regularly monitor and update GPOs as needed to ensure a secure and efficient environment. For advanced configurations or troubleshooting, refer to Microsoft's official documentation on Group Policy Management.





