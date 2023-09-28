# Learning Path 5 - Lab 5 - Exercise 2 - Implement a Safe Links Policy

## Lab scenario

Having created a Safe Attachments policy, Holly Dickson now wants to create a Safe Links policy and then validate the policy to ensure that it works properly.

>**IMPORTANT:** This lab exercise consists of two tasks. The first task creates a Safe Links policy, and then the second task validates the policy. The problem with this lab is that when you create a safe links policy, it takes at least 30 minutes for the new policy to propagate through the system. **This means that after performing Task 1, you must wait at least 30 minutes before performing Task 2. If you perform Task 2 immediately after performing Task 1, then Task 2 will fail.** After completing Task 1, you should continue with the training class. Your instructor will provide guidance on when you can perform Task 2 depending on the next break that occurs in the class schedule.

### Task 1 – Create a Safe Links Policy  

1. On LON-CL1, in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**.

2. After finishing the previous task, you should still be in the **Microsoft 365 Defender** portal. If not, then in your browser, enter **https://security.microsoft.com** in the address bar.

3. In the **Microsoft 365 Defender** portal, you should still be on the **Safe attachments** page after completing the previous task. In the navigation thread at the top of the page (**Policies & rules > Threat policies > Safe attachments**), select **Threat policies**.

    >**NOTE:** If you had closed the **Safe Attachments** tab after the prior task, then navigate to the **Threat policies** page by selecting **Policies & rules** in the left-hand navigation pane, and then selecting **Threat policies**.

4. In the **Threat policies** window, under the **Policies** section, select **Safe Links**. 

5. On the **Safe links** page, select **+ Create** on the menu bar. This initiates the **Create safe links policy** wizard.

6. On the **Name your policy** page, enter **LinkPolicy1** in the **Name** field and then select **Next**.

7. On the **Users and domains** page, enter **on** in the **Domains** field. In the menu of suggested domains that appears, select Adatum's **yourtenant.onmicrosoft.com** domain. Adatum's domain will now appear below the **Domains** field. Select **Next**.

8. On the **URL & click protection settings** page, update the following settings and then select **Next**: 

    - Under the **Email** section, verify that all check boxes are selected (if any are not selected by default, then select them now):
    - Under the **Click protection settings** section:
        - **Track user clicks** - Adatum does not want to track user clicks, so clear this check box if it's selected by default
   
9. On the **Notification** page, verify the **Use the default notification text** option is selected (if necessary, select it now) and then select **Next**.

10. On the **Review** page, review the options that you selected. If any need to be corrected, select the appropriate **Edit** option and make the necessary corrections. Once they all appear correct, select **Submit**. 

11. On the **New Safe Links policy created** page, select **Done**. Once the **LinkPolicy1** policy is created, it will appear in the Safe links list. 

12. In the navigation thread at the top of the page (**Policies & rules > Threat policies > Safe links**), select **Threat policies**.

13. In the **Threat policies** page, under the **Rules** section, select **Tenant Allow/Block Lists**.

14. On the **Tenant Allow/Block Lists** page, the **Domains & addresses** tab is displayed by default. Select the **URLs** tab.

15. On the **URLs** tab, select **+ Block** on the menu bar. In the **Block URLs** pane that appears, enter **http://tailspintoys.com** in the **Add URLs with wildcards (20 max)** field and then select **Add**.

    >**STOP!!** As mentioned at the start of this lab exercise, now that you have created a Safe Links policy, you must wait at least 30 minutes for the policy to propagate through the system before you can perform the next task in this exercise. 

    >**Do NOT proceed to the next task!** You can continue with the training course and perform the next task when your instructor feels it's appropriate given the class' training schedule. 

### Task 2 – Validate the Safe Links policy

1. On LON-CL1, in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**.

2. In your **Microsoft Edge** browser, select the **Home | Microsoft 365** tab and then in the column of app icons on the left side of the screen, select the **Outlook** icon. This will open Holly Dickson's mailbox.

3. **Outlook** will open in a new tab in your browser, and Holly's **Inbox** will be displayed.

4. Select the **New mail** button in the upper left part of the screen.

5. In the email form that appears in the right-hand pane, enter the following information:

    - To: You will be sending an email to the ODL user, so enter **ODL** in the **To** field and then select the **ODL user** email address from the user list.

    - Add a subject: **Free stuff for Adatum users**

    - Body of the message: **Please click on me for free toys from Tailspin Toys.**

6. Select the entire text string that you just added in the body of the message.

7. A row of formatting icons should appear. Select the **Link** icon, which depicts two half-ovals with a line in between. 

8. In the **Insert link** window that appears, the text that you highlighted in the body of the message should be displayed in the **Display as** field. In the **Web address (URL)** field, enter the following URL: **http://tailspintoys.com/aboutus/freetoys**.

9. Select **OK**. In the body of the email, the message should now be hyperlinked. 

10. Select the **Send** button. Select Holly's **Sent Items** folder to verify the message was sent.

11. You now want to go the ODL user's Inbox in Outlook and validate whether the Safe Links policy you created in the prior task worked on the email that you just sent from Holly to the ODL user.<br/>

    To do this, you must first switch to the Client 2 VM (**LON-CL2**). 

12. At the end of Lab 2, you should have logged into LON-CL2 as the local **Administrator** account (lon-cl2\admin).
    
    >**Note:** if you are logged in as Laura Atkins, then navigate back to the hyper-v manager, right click on **LON-CL2** VM and select **Turn-off**, right click again select **start**, then connect to the VM by right clicking on the **LON-CL2**, and select **connect**. Select **Other user**, and then log in as the local **(lon-cl2\admin)** with a password of **Pa55w.rd**.

13. On **LON-CL2**, select the **Microsoft Edge** icon in the taskbar, maximize the window and then enter the following URL in the address bar: **https://outlook.office365.com**

14. In the **Pick an account** window, select **Use another account**, and then in the **Sign in** window, enter the username and password for the ODL user account.

15. In the **Enter password** window, enter the tenant password provided by your lab hosting provider and select **Sign in**.

16. As you can verify that you haven't recieved the email from Holly's account, because the content is malicious.

19. You should now prepare LON-CL2 for the next lab that will use it. In your Edge browser, in the Outlook tab, select the circle with the **O1** initials in the upper right-hand corner. In the **ODL user** profile window that appears, select **Sign out**.

20. Once you are signed out of Outlook, close the Edge Browser. LON-CL2 is now ready for use in Lab 6.

## Review

In this lab, you have:

- Created a Safe Links Policy.
- Validated the Safe Links policy.

## You have successfully completed Lab 05. Proceed to the next exercise.

