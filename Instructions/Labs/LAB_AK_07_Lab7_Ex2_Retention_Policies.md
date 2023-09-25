# Learning Path 7 - Lab 7 - Exercise 2 - Configure In-place Archiving and Retention Policies  

## Lab scenario

In this exercise, you will use the the Microsoft Exchange admin center to enable In-place archiving for Holly Dickson's mailbox. You will then configure two retention policies through the Microsoft Purview portal. 

### Task 1 – Activate In-Place Archiving for a new user's mailbox

1. On LON-CL1, in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**.

2. In Microsoft Edge, in the **Microsoft 365 admin center**, under the **Admin centers** group, select **Exchange** to open the Exchange admin center.

5. In the **Exchange admin center**, the **Manage mailboxes** page appears by default. Note the users who have an **Archive status** that is set to **Active**. These archive mailboxes were enabled when the VM lab environment was built for this training course and these users were preconfigured in the tenant. However, since you added Holly's user account in one of the first labs at the start of this course, her archive mailbox is **Disabled** by default. 

5. To enable Holly’s archive mailbox, select **Holly Dickson** in the user list. In the **Holly Dickson** pane that appears, select the **Others** tab. In the **Mailbox archive** section, note that Holly's archive mailbox is disabled. In this group, select **Manage mailbox archive**. 

6. In the **Manage mailbox archive** pane that appears, select the toggle switch for **Mailbox archive status** to change it to **Enabled**. Select **Save** and then close the pane.

7. It might take a few moments to create Holly's archive mailbox. In the **Manage mailboxes** page, select the **Refresh** icon on the menu bar above the list of users. Holly's archive mailbox should now be **Active** once the archive mailbox is created. You may have to wait a minute or two and refresh again until **Active** appears.

8. In your Microsoft Edge browser, leave your Edge browser and all its tabs open for the next task. 
 

### Task 2 – Create an email retention policy for test users

1. On LON-CL1, your Microsoft Edge browser should still have the **Microsoft 365 admin center** open. Select the tab for the **Microsoft 365 admin center**. In the left-hand navigation pane, under the **Admin centers** section, select **Compliance**. Doing so will open the **Microsoft Purview** portal.

2. In the **Microsoft Purview** portal, in the left-hand navigation pane, select **Data lifecycle management**, and then select **Microsoft 365**.

3. In the **Data lifecycle management** window, in the list of tabs that appear across the top of the page, select **Retention policies**.

4. On the **Retention policies** tab, select **+ New retention policy** on the menu bar. This initiates the **Create retention policy** wizard.

5. On the **Name your retention policy** page, enter **Test user email retention** in the **Name** field and then select **Next**.

7. On the **Policy Scope** field, select **Static** and then select **Next**.

8. On the **Choose the type of retention policy to create** field, select **Static** and then select **Next**.

9. On the **Choose where to apply the policy** page, note the location. It's currently set to include **All recipients**. You want to change this to just apply to Joni Sherman and Lynne Robbins' mailboxes. Under **All mailboxes**, select **Edit**.

10. In the **Exchange mailboxes** pane that appears, hover your mouse over **Joni Sherman** and then select her check box. Do the same for **Lynne Robins**. 

	>**Note:** If you select a user's name, the other check boxes that have been selected will be unselected. To select multiple users, you must hover your mouse over each user's name and select their check box that appears. 

10. Once both check boxes are selected, select **Done**.

11. On the **Choose where to apply the policy** page, the **Exchange mailboxes** location should now indicate that **2 mailboxes** are included.  Since this policy will only apply to Exchange mailboxes for Joni and Lynne, set the **Status** toggle switch to **Off** for all other locations in which it's currently set to On (**SharePoint sites**, **OneDrive accounts**, and **Microsoft 365 Groups**). Select **Next**.

12. On the **Decide if you want to retain content, delete it, or both** page, verify the **Retain items for a specific period** option is selected (if necessary, select it now). Then enter the following information for this option: 

	- Retain items for a specific period - select in this field, and in the drop-down menu that appears, select **Custom**. Three fields will appear - years, months, and days. For testing purposes, Holly wants to test email retention for emails in Joni and Lynne's mailboxes by only retaining emails that are less than one year old. As such, set the time periods to the following values: **Years - 1, Months - 0, Days - 0**.

	- Start the retention period based on - **When items were created**

	- At the end of the retention period - **Delete items automatically**

13. Select **Next**.

14. On the **Review and finish** page, review your selections. If anything needs to be changed, select the appropriate Edit link and make the necessary changes. Otherwise, if everything is correct, select **Submit**.

15. On the **You successfully created a retention policy** window, select **Done**.

16. Leave the **Data lifecycle management** tab open in your Edge browser as you will create another retention policy in the next task.


### Task 3 – Create an email retention policy for all users

1. On LON-CL1, your Edge browser should still have the **Microsoft Purview** portal open from the prior task, and it should be displaying the **Data lifecycle management** window.

2. In the **Data lifecycle management** window, in the list of tabs that appear across the top of the page, select **Retention policies** (if another tab is selected).

3. On the **Retention policies** tab, select the check box next to **Test user email retention**, and then select **Disable policy** on the menu bar.  Once the policy is disabled, a message will briefly appear at the top of the page indicating the policy is disabled. You can test this out by once again selecting the check box next to **Test user email retention**. Note that the menu bar includes an **Enable policy** option. This option indicates the policy is currently disabled. You can now proceed to the remaining steps in this task to create Adatum's official, organization-wide email retention policy.

4. On the **Retention policies** tab, select **+ New retention policy** on the menu bar. This initiates the **Create retention policy** wizard.

5. On the **Name your retention policy** page, enter **Adatum email retention** in the **Name** field and then select **Next**.

7. On the **Policy Scope** field, select **Static** and then select **Next**.

7. On the **Choose the type of retention policy to create** field, select **Static** and then select **Next**.

8. On the **Choose where to apply the policy** page, this policy will only apply to **Exchange mailboxes**. Ensure that it's **Status** is set to **On**. Set the **Status** toggle switch to **Off** for all other locations that are turned **On** by default. **Exchange mailboxes** should be the only location whose **Status** is set to **On**. 

9. For the **Exchange mailboxes** location, note that it's currently set to include **All mailboxes**. Do not change this value, since you want this policy to apply to all user mailboxes. Select **Next**.

10. On the **Decide if you want to retain content, delete it, or both** page, verify the **Retain items for a specific period** option is selected (if necessary, select it now). Then enter the following information for this option: 

	- Retain items for a specific period - **5 years**

	- Start the retention period based on - **When items were last modified**

	- At the end of the retention period - **Delete items automatically**

11. Select **Next**.

12. On the **Review and finish** page, review your selections. If anything needs to be changed, select the appropriate Edit link and make the necessary changes. Otherwise, if everything is correct, select **Submit**.

13. On the **You successfully created a retention policy** window, select **Done**.

14. In your Edge browser, leave all the tabs open as you proceed to the next exercise.

You have now created a new retention policy in the Microsoft Purview portal that retains all Exchange emails from all mailboxes for 5 years after the last modification.

## Review

In this lab, you have:

- Activated In-Place Archiving for a new user's mailbox.
- Created an email retention policy for test users.
- Created an email retention policy for all users.

 # Proceed to Lab 7 - Exercise 3
 
