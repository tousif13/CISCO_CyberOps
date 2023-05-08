# Lab - Create User Accounts

## Part 1: Creating a New Local User Account

### Step 1: Open the User Account Tool.

* Log on to the Windows PC with an Administrator account. The account TOUSIF is used in this example.
* Click Start > search Control Panel. Select User Accounts in the Small icons view. To change the view, select Small icons in the View by drop down list.

### Step 2: Create a user account.

* In the User Accounts window, click Manage another account.

![image](https://user-images.githubusercontent.com/33444140/236889735-89627144-57ca-4e2a-9f33-230e7d2176bb.png)

* In the Manage Accounts window, click Add a new user in PC settings.
* In the Settings window, click Add someone else to this PC.
* In the How will this person sign in? window, click I don't have this person's sign-in information.
* In the Let's create your account window opens, click Add a user without a Microsoft account.
* In the Create an account for this PC window, provide the necessary information to create the new user account named User1. Click Next to create the new user account.
* Question: What type of user account did you just create?

    Created a local user account. It is a user account that is not linked to a Microsoft account and is specific to the computer where it was created.

* Navigate to C:\Users folder. Right-click the User1 folder and select Properties, and then the Security tab.

![image](https://user-images.githubusercontent.com/33444140/236892651-28f9da26-a5d5-4748-8b7d-8548d9133a65.png)

* Open the folder that belongs to TOUSIF. Right-Click the folder and click Properties tab.

![image](https://user-images.githubusercontent.com/33444140/236893157-800c48d7-6290-4c80-871a-c30e8bc76350.png)

* Log out of User1 account. Log back in as CyberOpsUser.
* Navigate to C:\Users folder. Right-click the folder and select Properties. Click the Security tab.

![image](https://user-images.githubusercontent.com/33444140/236893649-693eebaa-1ae5-4761-886c-ef5ed5737c92.png)

## Part 2: Modifying Local User Accounts

### Step 1: Change the account type.
* Navigate to the Control Panel and select User Accounts. Click Manage another account. Select User1.
* In the Change an Account window, click the User1 account. Click Change the account type.
* Select the Administrator radio button. Click Change Account Type.
![image](https://user-images.githubusercontent.com/33444140/236895790-f0424db7-dca1-486f-b289-1dd608ef52d7.png)

* Now the account User1 has administrative rights.

### Step 2: Delete the Account
![image](https://user-images.githubusercontent.com/33444140/236896185-81e1630e-6263-466e-bba8-3066d9c19a5b.png)

The user1 is deleted

![image](https://user-images.githubusercontent.com/33444140/236896283-671f96e6-1702-4750-908e-e1ddcf154371.png)

### Reflection Questions

1. Why is it important to protect all accounts with strong passwords?
    
> Protecting user accounts with strong passwords is essential because weak passwords can leave accounts vulnerable to hacking, identity theft, and other cyber attacks. When an account is hacked, the attacker may gain access to sensitive information, such as personal information, financial information, or sensitive business data. This information can be used for a variety of malicious purposes, including identity theft, financial fraud, or corporate espionage. In addition, a hacked account may be used to launch attacks on other users, further propagating the cyber threat.

2. Why would you create a user with Standard privileges?

> Creating a user account with standard privileges is a common practice in computer security to ensure that the user has limited access to the system and its resources
