# Learning Path 8 - Lab 8 - Exercise 2 - Test the DLP Policy

## Lab scenario

Holly Dickson is now at the point in her pilot project where she wants to test the DLP policy related to emails that contain sensitive information that you created in the previous lab exercise. 

>**NOTE:** We have intermittently experienced issues in the past where DLP policies and policy tips do not work as expected in this lab exercise. This is due to throttling issues that sometimes occur between our VM lab environment and the Microsoft 365 trial tenant. This is not indicative of the normal experience within Microsoft 365 production environments. It is also not indicative of the normal training experience. We apologize if you run into this issue during this lab exercise.

### Task 1 – Test the first DLP Policy rule


1. On LON-CL1, in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**. 

2. You will now send an email from Holly to Lynne Robbins, and you will include an IP address in the body of the email. In **Microsoft Edge**, select the **Microsoft Office Home** tab, and then select the **Outlook** icon in the column of app icons on the left-side of the screen. When Outlook on the web opens, you should be automatically logged in as Holly Dickson.  

	>**Note:** If **Outlook on the web** was already open, then verify that you're logged in as **Holly** by checking the user icon in the upper right corner (the **HD** circle). If Outlook was open for any other user, then close the tab and repeat the instructions in this step to open Outlook on the Web for Holly.

3. In the upper left corner of the screen, select **New mail**. 

4. In the message pane that appears on the right-side of the screen, enter the following information:

	- To: enter **Lynne** and then select **Lynne Robbins** from the user list that appears

	- Add a subject: **DLP Policy Test 1**

	- Message area: **Hey Lynne - I will configure this IP address: 192.168.0.1**

5. Select **Send**.

6. Select Holly's **Sent Items** folder to verify the email was sent.

7. Select Holly's **Inbox** folder. Holly should receive an email from **Microsoft Outlook** with the subject: **Notification: DLP Policy Test 1**. Select this email and review its content. 

<!-- 8. Switch to **LON-CL2**. 

9. If you need to sign into the VM, the local **administrator** account should appear by default, so enter **Pa55w.rd** in the **Password** field to log in. 

10. On the taskbar, select the icon for the **Edge** browser.

11. In the Edge browser, enter the following URL: **https://outlook.office365.com**

12. In the **Pick an account** window, select Lynne Robbins' account, enter the password and then select **Sign in**. On the **Stay signed in** window, select the **Don't show this again** check box and select **Yes**.

13. In Lynne's Inbox, verify that she received the email from Holly Dickson that has the subject line: **DLP Policy Test 1**. Select the message to verify the content containing the IP address was not removed. 

	>**Note:** if you haven't recieved the email on Lynne's account, you have wait atleast -->

14. Leave the Outlook tab open in the Edge browser for the next task.

15. Switch back to **LON-CL1**. 

	
### Task 2 – Test the second DLP Policy rule  

1. On LON-CL1, in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**. 
	
2. You will now send a second message from Holly to Lynne that contains multiple IP addresses. Repeat the process as before for creating an email to Lynne Robbins with the following information: 

	- Add a subject: **DLP Policy Test 2**

	- Message area: **Hey Lynne - I will test the following IP addresses: 192.168.0.1 and 172.16.0.1**

3. Select **Send**. You should immediately receive a **Message blocked** email, on the inbox with a subject **Message Blocked: DLP Policy Test 2**. 

4. Select Holly's **Sent Items** folder to verify the email is sent.

<!-- 6. To send this email, you must override the block BEFORE you select the **Send** button. To override the block, in the policy tip that appears at the top of the message, select **Show details**.

7. In the detail message that appears in the policy tip, select **Override**.

8. In the dialog box that appears, the **I have a business justification** option is selected by default. Leave this option selected and enter **Lynne must be informed of the IP addresses I'm testing** in the **Enter explanation here** field. Select **Override**.	

	>**Note:** how the policy tip message has changed to indicate you have chosen to send the message even though it appears to contain sensitive information.

9. Select Holly's **Sent Items** folder to verify the email was sent.

10. Select Holly's **Inbox** folder. Holly should receive an email from **Microsoft Outlook** with the subject: **Notification: DLP Policy Test 2**. Select this email and review its content.
	
11. Switch to **LON-CL2**. 

12. You should still be logged into **Outlook on the Web** in the LON-CL2 VM as **Lynne Robbins**. In your **Edge** browser, Lynne’s mailbox should still be open in **Outlook on the web** from when you last used it in the previous task.

13. In Lynne's Inbox, verify that she received the email from Holly Dickson that has the subject line: **DLP Policy Test 2**. Select the message to verify the content containing the IP addresses was not removed. -->

14. Leave the Outlook tab open in the Edge browser for the next task.

15. Switch back to **LON-CL1**.

## Review

In this lab, you have:

- Tested the first DLP Policy rule.
- Tested the second DLP Policy rule.

# You have successfully completed Lab 08, proceed with the next labs.
