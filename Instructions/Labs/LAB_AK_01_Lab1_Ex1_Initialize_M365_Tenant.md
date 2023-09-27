# Learning Path 1 - Lab 1 - Exercise 1 - Initialize your Microsoft 365 Tenant 

## Lab scenario

Adatum Corporation is a subsidiary of Contoso Electronics. Adatum runs its legacy applications (such as Microsoft Exchange Server 2019) in an on-premises deployment. However, it recently subscribed to Microsoft 365, thereby creating a hybrid deployment in which it must synchronize its on-premises and cloud deployments. 

As Adatum's Microsoft 365 administrator, you have been tasked with deploying Microsoft 365 in Adatum’s hybrid deployment using a virtualized lab environment. In this exercise, you will set up Adatum's Microsoft 365 trial tenant, and your instructor will guide you on how to obtain your Microsoft 365 credentials in your lab-hosted environment. You will use these credentials throughout the remaining labs in this course. 

In your lab environment, your lab hosting provider has already obtained a Microsoft 365 trial tenant for you. Your lab provider has also created two admin accounts that you will use in your VM lab environment: 

- A local administrator account for Adatum's on-premises environment (Adatum\Administrator).
- A default tenant admin account in Microsoft 365 (the display name for this user account is ODL user). 

You will log into the Client 1 PC (LON-CL1) using the local Adatum\Administrator account. When you access Microsoft 365 for the first time, you will initially log in using the Microsoft 365 tenant admin account (ODL user). You will then update Adatum's Microsoft 365 organizational profile, and you'll prepare your tenant for Microsoft Entra ID and for later labs using Information Rights Management, audit alerts, Microsoft Graph PowerShell, and sensitivity labels.

>**Important:** You can find all the users usernames which is required in this lab, inside the Azure Portal. You can log into the portal using ODL credentials, in the **Search resources, services and docs** search for **Users**, select it. As you can see all the users are listed. 

>**Note:** Open this page for further use.
 
## Pre-requisite

1. In **Type here to search** type and search for **Hyper-V Manager**.

2. On the Virtual Machines section, it will show the all the virtual machines that are in running state, right click on **LON-CL1** VM, select **Connect**, on the **Connect to LON-CL1** select **Connect**.

3. Log into **LON-CL1** as the local **Administrator** account that was created by your lab hosting provider with the password **Pa55w.rd**. 

4. Double-click on **Microsoft Edge**, in the search bar copy and paste the URL to open [Azure Portal](https://portal.azure.com/#home), in **search resources, services, and docs**, type and search for **Microsoft Entra ID**, select **Users** from the left-hand navigation pane, under **All users** pane search for **odl_user <inject key="DeploymentID" enableCopy="false"/>**, select the user.

5. On the left-hand side navigation, under **Manage** section, select **Licenses**, select **+ Assignments**, under **Update license assignments**, tick the check box of **Microsoft 365 Business Premium**, and select **Save**.

6. Repeat the steps 4-5 for the **Alex Wilber, Allan Deyoung, Joni Sherman, Lynne Robbins, Diego Siciliani, Isaiah Langer, Megan Bowen, Nestor Wilke, and Patti Fernandez**.

7. Close the **Licenses** tab.

8. In **Type here to search**, type and select **Windows Powershell ISE**, and run the following commands to assign the usage location to all the users:

	```powershell
    Connect-AzureAD
    ```
	>**Note:** Provide the ODL credentials, on the Sign-in page, enter the username **odl_user_<inject key="DeploymentID" enableCopy="false"/>@yourtenant.onmicrosoft.com** (where yourtenant is the tenant prefix provided by your lab hosting provider), and enter the password **<inject key="AzureAdUserPassword"></inject>**

	```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -UsageLocation US
	```

9. Close the **Windows Powershell ISE**.

10.  Now, open the Edge browser and use this URL **https://admin.microsoft.com/Adminportal/Home** to open the Microsoft 365 admin center. On the Sign in page, enter the username **odl_user_<inject key="DeploymentID" enableCopy="false"/>@yourtenant.onmicrosoft.com** (where yourtenant is the tenant prefix provided by your lab hosting provider), and enter the password **<inject key="AzureAdUserPassword"></inject>**. It will open the Microsoft 365 admin center page.

11.  On the **the Microsoft 365 admin center** page, select **Users** from the left-hand navigation pane, and select **Active users**. Hover the mouse on the Alex wilber, as you can see the reset a password icon, select it. On the **Reset Password** page, if the **Automatically create a password** and **Require this user to change their password when they first sign in** checkboxes are checked, then uncheck both boxes, and inside **Password** enter any password of your choice (write down the password somewhere for further use). After entering the password, select **Reset Password**. On the password has been reset page, select **Close**.

12.  Repeat step-11 for the **Allan Deyoung, Joni Sherman, Lynne Robbins, Diego Siciliani, Isaiah Langer, Megan Bowen, Nestor Wilke, and Patti Fernandez**.

13.  You have successfully reset the password for all these users **Alex Wilber, Allan Deyoung, Joni Sherman, Lynne Robbins, Diego Siciliani, Isaiah Langer, Megan Bowen, Nestor Wilke, and Patti Fernandez**. Close the tab and you can start with the task-1.

### Task 1- Set up Adatum's Organization Profile

1. On the taskbar at the bottom of your screen, select the **Microsoft Edge** icon. If necessary, maximize your browser window when it opens.

2. In your Edge browser, go to the **Microsoft 365 Home** page by entering the following URL in the address bar: **https://portal.office.com** 

3. In the **Sign in** dialog box, in the **Enter username** dialog box, enter the username **odl_user_<inject key="DeploymentID" enableCopy="false"/>@yourtenant.onmicrosoft.com** (where yourtenant is the tenant prefix provided by your lab hosting provider), in the **Microsoft 365 Tenant Username**, select **Next**.

5. In the **Enter password** dialog box, enter the password <inject key="AzureAdUserPassword"></inject> page in the **Microsoft 365 Tenant Password** and then select **Sign in**.

	>**Note:** if **More information required** page appears, proceed with the steps and provide authentication.

6. On the **Stay signed in?** dialog box, select the **Don’t show this again** check box and then select **Yes.** On the **Save password** dialog box that appears, select **Never**.

7. If a **Welcome to Microsoft 365** dialog box appears in the middle of the screen, there's no option to close it. Instead, to the right of the window, select the forward arrow icon (**>**) two times and then select the check mark icon to advance through the slides in this messaging window. 

8. If a **Find more apps** window appears, select the **X** in the upper right-hand corner of the window to close it. 

9. The **Welcome to Microsoft 365** page appears in your Edge browser in the **Home | Microsoft 365** tab. This is the ODL user's Microsoft 365 home page.

	>**Note:** if it doesn't open, then in the Edge browser paste this URL **admin.microsoft.com**.

	>**Note:** Notice the initials **O1** that appear in a circle in the top-right corner of the screen. These are the initials of the **ODL user** account, which is the tenant admin account that you just signed in as. However, when a user such as the ODL user has no picture assigned to it, the user's initials are displayed in place of the picture.

10. On the **Welcome to Microsoft 365** page, in the list of application icons that appear in the left-hand pane, select **Admin**, this opens the **Microsoft 365 admin center** in a new browser tab. 

	![](../Images/MS-102-image-1.png)

11. In the **Microsoft 365 admin center**, select **Show all** in the left-hand navigation pane and then select **Settings**. In the **Settings** group, select **Org settings**. 

	![](../Images/MS-102-image-2.png)

12. On the **Org settings** page, the **Services** tab is displayed by default. Select the **Organization profile** tab.

13. In the **Organization profile** tab, select **Organization information** from the list of profile data.

	![](../Images/MS-102-image-3.png)

12. In the **Organization information** pane that appears, enter the following information:

    - Name: **Adatum Corporation** (Note: Adatum Corporation is a subsidiary of Contoso Inc. The Microsoft trial tenant that your lab hosting provider obtained for this lab may have been originally assigned to Contoso. If **Contoso** (or any other value) appears as the organization name, then change it to **Adatum Corporation**.)

    - Street Address: **555 Main Street**

    - City: **Redmond**

    - State or province: **Washington**

    - ZIP or postal code: **98052**

    - Phone: do not change

    - Technical contact: do not change

    - Preferred language: **English**

13. Select **Save**.

14. At the top of the **Organization information** pane, note the message indicating the **Saved**. Select the **X** in the upper right-hand corner to close the pane.

15. Back on the **Organization profile** tab, in the list of organization profile data, select **Release preferences**.

    >**Note:** One of the benefits of Microsoft 365 is its ability to have the latest features and updates automatically applied to your environment. This process can reduce maintenance costs and overhead for an organization and allow early-adopter users to test new features. By setting up your **Release preferences**, you can control how and when your Microsoft 365 tenant receives these updates.

16. In the **Release preferences** pane that appears, select the **Targeted release for select users** option and then select **Save**.

	>**Note:** the **Targeted release for select users** option enables you to create a control group of users who will preview updates so that you can prepare the updates for your entire organization. The **Targeted release for everyone** option is more commonly used in development environments, where you can get updates early for your entire organization. In non-development environments, such as Adatum, targeted release to a select group of users is a more typical preference as it enables an organization to control when it wants to make updates available to everyone once they've been reviewed by the control group.

	![](../Images/MS-102-image-4.png)

17. In the **Release preferences** pane, below the list of release options, select the **Select users** option.

18. In the **Choose users for targeted release** pane that appears, select inside the **Who should receive targeted releases?** field. In this list, select each of the following users.

    >**Note:** You must select each user, one at a time. After selecting a user, you must select inside the **Who should receive targeted releases?** field again to re-display the list so that you can select the next user. 

	- **Alex Wilber**
	- **Joni Sherman**
	- **Lynne Robbins**
	- **ODL_User <inject key="DeploymentID" enableCopy="false"/>**

	>**Note:** Alex, Joni, and Lynne are part of Holly's Microsoft 365 pilot team. Their accounts will be used throughout the labs for this course.
    
19. Select **Save**.

20. At the top of the **Release preferences** pane, note the message indicating the 4 users were added to the targeted release. Select the **X** in the upper right-hand corner to close the pane. 

21. Remain logged into **LON-CL1** with Microsoft Edge open to the **Microsoft 365 admin center** for the next task.

### Task 2- Create a custom theme for Adatum's pilot project team

1. You should still be logged into LON-CL1 as the local **adatum\administrator** account, and in your Edge browser, you should still be logged into Microsoft 365 as the **ODL user**. 

2. In the **Microsoft 365 admin center**, select **Teams & groups** in the left-hand navigation pane, and then under it, select **Active teams & groups**. 

3. In the **Active teams and groups** page, there's a tab for viewing each of the group types. this tab displays the existing Microsoft 365 groups. Select the **+ Add a Microsoft 365 group** option that appears on the menu bar above the list of Microsoft 365 groups. This initiates the **+ Add a Microsoft 365 group** wizard. 

	![](../Images/MS-102-image-5.png)

5. In the **Set up the basics** page, enter **M365 pilot project** in the **Name** field, and then enter **Members of the Microsoft 365 pilot project team** in the **Description** field (Note: even if you don't enter a description, you must still select into this field to enable the **Next** button). Select **Next**.

	![](../Images/MS-102-image-6.png)

6. You will now assign the ODL user as owner of the **M365 pilot project** group. In the **Assign owners** window, select **+ Assign owners**.
	
7. In the **Assign owners** pane that appears, select the check box next to **odl_user <inject key="DeploymentID" enableCopy="false"/>**, and then select the **Add (1)** button at the bottom of the pane.

	![](../Images/MS-102-image-7.png)

8. On the **Assign owners** page, ODL user should appear as owner of the group. Select **Next**.

9. You will now assign members to the M365 pilot project group. In the **Add members** page, select **+ Add members**.

10. In the **Add members** pane that appears, select the check boxes next to the following users: **Alex Wilber**, **Allan Deyoung**, **Diego Siciliani**, **Isaiah Langer**, **Joni Sherman**, **Lynne Robbins**, **Megan Bowen**, **ODL user**, **Nestor Wilke**, and **Patti Fernandez**. Then select the **Add (10)** button at the bottom of the pane.

11. On the **Add members** page, verify these 10 users are listed as members of the group. If you missed a user, select **+ Add members** and then add any users that you missed. When all 10 users appear on this page, select **Next**.

12. In the **Edit settings** page, enter the following information:

	- Enter **m365pilotproject** in the **Group email address** field.
	- In the **Privacy** field, select **Private**.
	- Under the **Add Microsoft Teams to your group** section, verify the **Create a team for this group** check box is selected (select it if it's blank), and then select **Next**.

13. In the **Review and finish adding group** page, review the content that you entered. If anything needs to be fixed, select **Edit** under the specific area that needs adjustment, make any necessary corrections, and then select **Next** to continue back to this page. Once everything is correct, select **Create group**.

14. Once the **M365 pilot project group created** window appears, note the comment at the top of the page that it may take 5 minutes for the new group to appear in the list of Active groups.  

15. Select **Close**. This returns you to the **Active teams and groups** page, which should display the **Teams & Microsoft 365 groups** group tab. Since the M365 pilot project group was a Microsoft 365 group, it should eventually display on this tab. If necessary, select the **Refresh** option on the menu bar until you see the M365 pilot project group in the list of Teams & Microsoft 365 groups.

15. In the **Microsoft 365 admin center**, under the **Settings** group in the navigation pane, select **Org settings**. 

16. On the **Org settings** page, select the **Organization profile** tab.

17. In the list of organization profile data, select **Custom themes**.

	![](../Images/MS-102-image-8.png)

18. In the **Customize Microsoft 365 for your organization** pane that appears, you can customize the default theme that users see when signed into Microsoft 365, and you can add additional custom themes. Select the **+ Add theme** option.

26. In the **Customize Microsoft 365 for your organization** pane that appears, notice how it displays the **Default theme**. Select the **Default theme**. 

27. On the **Default theme** pane, notice how the **Show the user's display name** option is not selected. Select that check box, and **Save it**. Select the back arrow at the top of the pane to return to  the **Customize Microsoft 365 for your organization** pane.

	>**Note:** Holly decides to make the **Show the user's display name** option a permanent feature, she selected this option in the **Default theme** pane so that it applies to all Adatum users.

20. In the **Customize Microsoft 365 for your organization** pane that appears, you can customize the default theme that users see when signed into Microsoft 365, and you can add additional custom themes. Select the **+ Add theme** option.

19. In the **New group theme** pane that appears, the **General** tab is displayed by default. Enter **M365 pilot project theme** in the **Name** field.

20. Select inside the **Groups** field. In the list of groups that appears, select **M365 pilot project** if it appears in the list of groups.

	>**Note:** If **M365 pilot project** doesn't appear in the list of groups, then enter **M365** in the **Groups** field. A search results box should appear that displays the **M365 pilot project** group. Select **M365 pilot project**. 

21. Select the **Show the user's display name** check box. This is the setting that Holly wants to customize for the M365 pilot project team members.
 
22. Select the **Logos** tab and take some time to review its options. Do the same for the **Colors** tab. Note the various theme and branding options that are available for you to update.

	>**Note:** For the purpose of this lab, you can change any of the options or leave the default values as is. For example, in your real-world environment, you can add the logo of your company and set the background image as the default for all your users. For this lab, feel free to change the colors for your navigation pane, text color, icon color, and accent color. 

	**Go ahead and explore the different options for this theme that will be used by the Microsoft 365 pilot project team members. Make any changes that you wish.** 

	>**Tip:** Some color patterns aesthetically distract users. If you do change any of the colors, it's recommended that you avoid using high contrasting colors together, such as neon colors and high-resolution colors like bright pink and white.

23. Select **Save**. Close the **M365 pilot project theme** pane once your changes are saved. 

24. Select the **Refresh** icon at the top of the screen, to the left of the address bar. Once the screen refreshes, note how the **ODL user** name appears to the left of the circle with the **O1** initials. The signed-in user's name now appears to the left of their profile picture or initials due to the custom theme that you just created.

25. In the list of organization profile data, select **Custom themes**.

	Close the **Customize Microsoft 365 for your organization** pane.

28. Remain logged into **LON-CL1** with Microsoft Edge open to the **Microsoft 365 admin center** for the next task.

### Task 3 - Enable Information Rights Management for SharePoint Online  

>**Important:** While you will validate IRM for Exchange and SharePoint in Lab 7, you must enable IRM for SharePoint Online now because it can take up to 60 minutes or more for IRM to show up in SharePoint Online. By the time you get to the validation exercise in Lab 7, IRM should have finished its internal configuration and you won’t have to wait for it to be present in SharePoint Online. Keep this time issue in mind if you plan to enable IRM in your real-world deployment.

1. You should still be logged into LON-CL1 as the local **adatum\administrator** account, and in your Edge browser, you should still be logged into Microsoft 365 as the **ODL user**. 

2. In the **Microsoft 365 admin center**, select **Show all** in the left-hand navigation pane to see all the navigation options. Under the **Admin centers** group, select **SharePoint**. This will open the **SharePoint admin center** in a new tab.

3. In the **Welcome to your new home page** window, select **Take the tour**.

4. In the **SharePoint admin center**, in the left-hand navigation pane, select **Settings**. 

5. At the bottom of the **Settings** page is a sentence that says **Can’t find the setting you’re looking for? Go to the classic settings page.** In this sentence, select the hyperlinked text that says: **classic settings page**.

6. On the classic **Settings** page, scroll down to the **Information Rights Management (IRM)** section. In the options to the right of this section, select the **Use the IRM service specified in your configuration** option, and then select the **Refresh IRM Settings** button.

7. Scroll to the bottom of the page and select the **OK** button. 

8. Once the changes have been saved, you will be returned to the top of the **Settings** page. In your browser, close the current tab that you're on. This will return you to the **Settings** page in the **SharePoint admin center**.

9. Close this **SharePoint admin center** tab in your Edge browser. Leave the other tabs open in your browser for the next task.


### Task 4 – Turn on Audit Logging to enable Alert Policies

1. You should still be logged into LON-CL1 as the local **adatum\administrator** account, and in your Edge browser, you should still be logged into Microsoft 365 as the **ODL user**. 

2. In the **Microsoft 365 admin center**, under the **Admin centers** section in the left-hand navigation pane, select **Security**. This will open the **Microsoft 365 Defender** portal in a new tab in your browser.

3. In the **Microsoft 365 Defender** portal, scroll down towards the bottom of the left-hand navigation pane and select **Audit**.

4. In the **Audit** window, wait a minute or so to see if a banner appears towards the top of the page that says: **Start recording user and admin activity**. If this banner appears, then auditing is NOT turned on for your organization. This banner is your prompt to turn on audit logging.

	>**Note:** Select this banner now to turn on audit logging, and on the **Security** pop-up select **Yes**, and if it says **We're updating your organization to support customization. Please allow 24 to 48 hours before you retry this operation.**, select **OK**.

5. In the **Audit** window, the banner will disappear once audit logging is turned on. In a later lab, you will return to this page to view audited activities that you completed during your lab work.  
 
6. Close the **Microsoft 365 Defender** tab in your Edge browser. Leave your browser open and proceed to the next task. 


### Task 5 – Install Microsoft Graph PowerShell   

1. On LON-CL1, you must open an elevated instance of **Windows PowerShell**. Type **power** in the Search box that appears in the bottom left corner of the taskbar. In the list of search results, right-click on **Windows PowerShell** (do not select Windows PowerShell ISE) and select **Run as administrator** in the drop-down menu that appears. 

2. Maximize your PowerShell window. In **Windows PowerShell**, type the following command at the command prompt to install the Microsoft Graph PowerShell module from the PowerShell Gallery and then press Enter:
	```powershell
    Install-Module Microsoft.Graph -Scope CurrentUser
    ```

3. You will be prompted to confirm whether you want to install the module from an untrusted repository (PSGallery). Enter **A** to select **[A] Yes to All** and then press Enter.  

    >**Note:** Your response will initiate the installation of all the Microsoft Graph sub-modules. Once all the installation messages (for each sub-module) have finished displaying, it will still take approximately 5 to 10 minutes to complete the Microsoft Graph PowerShell installation. During this time, the cursor will continue to blink below the untrusted repository message. This may be a good time to take a short break.

4. A command prompt will appear once Microsoft Graph PowerShell has been installed. Run the following command to see the complete list of sub-modules that were installed under the Microsoft.Graph primary module:  
	
	```powershell
    Get-InstalledModule Microsoft.Graph.* 
    ```

	>**Note:** The labs that use Microsoft Graph PowerShell in this course will use the following sub-modules: Microsoft.Graph.Identity.DirectoryManagement, Microsoft.Graph.Users, and Microsoft.Graph.Groups. To access the cmdlets for a sub-module, you must first import the sub-module. You can either import all 30+ sub-modules at one time using the "Import-Module Microsoft.Graph" command, or you can import each module that's needed to perform whatever function you're doing (for example, "Import-Module Microsoft.Graph.Users" to perform user maintenance) at a particular point in time. For the purpose of this training, since the later lab exercises will only use three sub-modules, you will NOT import all 40+ sub-modules now. Instead, you will wait to import these three sub-modules when they're needed in later labs. Proceed to the next step. 

5. PowerShell's execution policy settings dictate what PowerShell scripts can be run on a Windows system. Setting this policy to **Unrestricted** enables Holly to load all configuration files and run all scripts. At the command prompt, type the following command, and then press Enter:
	
	```powershell
	Set-ExecutionPolicy unrestricted
	```
6. If you are prompted to verify that you want to change the execution policy, enter **A** to select **[A] Yes to All.** 

6. Do **NOT** close your PowerShell window. Leave the Windows PowerShell window open but minimize it for now. Remain logged into LON-CL1 and keep your Edge browser open.


### Task 6 - Run a PowerShell script to create and publish a sensitivity label 

>**Note:** In the sensitivity label lab that you perform on the last day of class, you will create another label and label policy - just ones with different names. Their settings will be exactly the same as the ones created by this script. The sensitivity label lab will give you the experience of creating a label and publishing a label policy using the Microsoft 365 UI. However, when you perform the tasks to test the sensitivity label and label policy, you won't test the ones that you created and published in the UI, since they won't be available for testing until the next day. Instead, you will test the label and label policy that were created and published using the script that you run in this task. 

1. On **LON-CL1**, select the **File Explorer** icon from the Windows taskbar. Maximize the File Explorer window.

2. In **File Explorer**, navigate to the following folder location: **C:\Users\Administrator.ADATUM\Documents\Lab Setup**.

3. In the **Lab Setup** subfolder a .bat file named **LabSetup.bat** should exist. Right-click on the **LabSetup.bat** file and then select **Run as administrator**. Doing so will start the lab setup process.

    >**Note:** If a **Windows protected your PC** pop-up warning is displayed, select **More info** and then select **Run anyway** at the bottom of the pop-up to continue. A **Lab setup** window will appear on the screen.

4. It may take up to 1 minute before a **Sign in** window appears. Enter the **odl_user_<inject key="DeploymentID" enableCopy="false"/>@yourtenant.onmicrosoft.com** (where yourtenant is the tenant prefix provided by your lab hosting provider) on the **Enter username**, and then select **Next**. On the **Enter password** enter **<inject key="AzureAdUserPassword"></inject>** and then select **Sign in**.

5. A **Pick an account** window will appear. On this window, select **ODL user** from the list of available accounts. If prompted, enter the tenant admin password provided by your lab hosting provider and then select **Sign in**.

    >**Important:** The **Lab Setup** process has a time-out of 5 minutes. If you fail to type in your credentials within this 5 minute time frame, a pop-up message displaying **Lab Setup Failed. EXITING...** will appear. Select **Ok**, close the Microsoft Sign-on window, and repeat steps 3-5.

6. Once the lab setup process has completed, a pop-up message displaying **Lab Setup Completed. EXITING...** will appear. Select **Ok** and proceed.

    >**IMPORTANT:** It may take up to 5 minutes for the lab setup process to complete.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
- Click the Lab Validation tab located at the upper right corner of the lab guide section and navigate to the Lab Validation Page.
- Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

## Review

In this lab, you have:

- Learnt how to set up Adatum's Organization Profile.
- Created a custom theme for Adatum's pilot project team.
- Learnt how to enable Information Rights Management for SharePoint Online.
- Explored how to turn on Audit Logging to enable Alert Policies.
- Installed Microsoft Graph PowerShell.
- How to run a PowerShell script to create and publish a sensitivity label.


# Proceed to Lab 1 - Exercise 2 
