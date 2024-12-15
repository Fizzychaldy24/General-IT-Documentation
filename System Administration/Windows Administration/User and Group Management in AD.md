# User and Group Management in Active Directory

This guide provides instructions for managing user and group accounts in **Active Directory (AD)**. Managing users and groups is a core task for administrators to ensure proper access control and organization within the domain.

## Table of Contents
1. [Creating User Accounts](#creating-user-accounts)
2. [Modifying User Accounts](#modifying-user-accounts)
3. [Deleting User Accounts](#deleting-user-accounts)
4. [Creating Groups](#creating-groups)
5. [Adding Users to Groups](#adding-users-to-groups)
6. [Modifying Group Membership](#modifying-group-membership)
7. [Deleting Groups](#deleting-groups)
8. [Best Practices for User and Group Management](#best-practices-for-user-and-group-management)

## Creating User Accounts

To create a new user account in Active Directory:

1. **Open Active Directory Users and Computers**:
   - Go to **Server Manager** > **Tools** > **Active Directory Users and Computers**.

2. **Navigate to the Desired Organizational Unit (OU)**:
   - Right-click on the **Organizational Unit (OU)** where you want to create the user account, then select **New** > **User**.

3. **Fill in User Information**:
   - Enter the user's **First Name**, **Last Name**, and **User Logon Name** (this is the username they will use to log in).
   - Click **Next**.

4. **Set User Password**:
   - Enter a **password** for the user. You may also set the option to **User must change password at next logon** if required.
   - Click **Next**, then **Finish**.

5. **Verify User Creation**:
   - The new user will appear in the selected OU.

## Modifying User Accounts

To modify a user account:

1. **Open Active Directory Users and Computers**.
2. **Navigate to the User Account**:
   - Right-click the user account you wish to modify, and select **Properties**.
   
3. **Edit User Information**:
   - You can modify the **General**, **Account**, **Profile**, **Member Of**, and other tabs.
   - For example, you can change the **User logon name**, update **contact information**, or set **group memberships**.

4. **Save Changes**:
   - After making the necessary changes, click **OK** to save.

## Deleting User Accounts

To delete a user account:

1. **Open Active Directory Users and Computers**.
2. **Navigate to the User Account**:
   - Right-click the user account you wish to delete, and select **Delete**.
   
3. **Confirm Deletion**:
   - A confirmation message will appear. Click **Yes** to confirm the deletion.

4. **Check for Orphaned User Accounts**:
   - It’s a good idea to check whether the user account was removed properly and ensure there are no orphaned permissions or profiles left behind.

## Creating Groups

To create a new group:

1. **Open Active Directory Users and Computers**.
2. **Navigate to the Desired Organizational Unit (OU)**:
   - Right-click on the **OU** where you want the group to be created, and select **New** > **Group**.

3. **Set Group Name and Type**:
   - Enter the **Group Name** and select the **Group Scope** (e.g., **Global**, **Domain Local**, or **Universal**).
   - Select the **Group Type** (either **Security** for controlling access or **Distribution** for email distribution lists).

4. **Create the Group**:
   - Click **OK** to create the group.

## Adding Users to Groups

To add users to a group:

1. **Open Active Directory Users and Computers**.
2. **Navigate to the Group**:
   - Right-click the group you want to add users to and select **Properties**.
   
3. **Add Members**:
   - In the **Members** tab, click **Add**.
   - Enter the names of the users you want to add and click **Check Names** to resolve them.
   - Click **OK** to add the users to the group.

4. **Verify Membership**:
   - The users will now appear in the group’s **Members** list.

## Modifying Group Membership

To modify the members of a group:

1. **Open Active Directory Users and Computers**.
2. **Navigate to the Group**:
   - Right-click the group and select **Properties**.
   
3. **Modify Members**:
   - Under the **Members** tab, you can:
     - **Add** new members.
     - **Remove** existing members.
     - **Change membership type** for specific users if necessary.

4. **Save Changes**:
   - Click **OK** to save the changes.

## Deleting Groups

To delete a group:

1. **Open Active Directory Users and Computers**.
2. **Navigate to the Group**:
   - Right-click the group and select **Delete**.

3. **Confirm Deletion**:
   - A confirmation prompt will appear. Click **Yes** to delete the group.

## Best Practices for User and Group Management

1. **Use Descriptive Naming Conventions**:
   - Use clear, consistent names for users and groups. For example, `john.doe` for a user and `HR-Department` for a group.
   
2. **Leverage Organizational Units (OUs)**:
   - Organize users and groups into OUs based on departments, roles, or geographical locations to simplify management.

3. **Group Nesting**:
   - Nest groups within other groups to simplify permissions and management.

4. **Use Group Policies**:
   - Assign **Group Policy Objects (GPOs)** to control access, security settings, and other configurations for users and groups.

5. **Review Group Membership Regularly**:
   - Periodically review group memberships to ensure only necessary users have access to critical resources.

6. **Assign Permissions Based on Roles**:
   - Apply the **principle of least privilege** by assigning users to groups with the minimal necessary permissions.

7. **Monitor User and Group Activity**:
   - Regularly audit user and group activities using tools like **Event Viewer** or **PowerShell** scripts to ensure compliance with security policies.
