---
title: Set up Desktop Analytics
titleSuffix: Configuration Manager
description: A how-to guide for setting up and onboarding to Desktop Analytics.
ms.date: 06/14/2019
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: 7ff8d453-f24d-4230-a116-585190a663fc
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
---

# How to set up Desktop Analytics

> [!Note]  
> This information relates to a preview service which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.  

Use this procedure to sign in to Desktop Analytics and configure it in your subscription. This procedure is a one-time process to set up Desktop Analytics for your organization.  



## Initial onboarding

1. Open the [Desktop Analytics portal](https://aka.ms/desktopanalytics) in Microsoft 365 Device Management as a user with the **Global Admin** role. Select **Start**.  

    > [!Tip]  
    > To access the Desktop Analytics portal from the Configuration Manager console, go to the **Software Library** workspace, select the **Desktop Analytics Servicing** node, and select **Plan deployments**.

2. On the **Accept service agreement** page, review the service agreement, and select **Accept**.  

3. On the **Confirm your subscription** page, review the list of required qualifying licenses. Switch the setting to **Yes** next to **Do you have one of the supported or higher subscriptions**, and then select **Next**.  

4. On the **Give users access** page:

    - **Allow Desktop Analytics to manage Directory roles on your behalf**: Desktop Analytics automatically assigns the **Workspace Owners** the **Desktop Analytics Administrator** role. If those groups are already a **Global Admin**, there's no change.

        If you don't select this option, Desktop Analytics still adds users as members of the security group. A **Global Admin** needs to manually assign the **Desktop Analytics Administrator** role for the users.   

        For more information about assigning administrator role permissions in Azure Active Directory and the permissions assigned to **Desktop Analytics Administrators**, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).  

    - Desktop Analytics preconfigures the **Workspace Owners** security group in Azure Active Directory to create and manage workspaces and deployment plans. 

        To add a user to the group, type their name or e-mail address in the **Enter name or email address** section. When finished, select **Next**.

5. On the page to **Set up your workspace**:  

    > [!Note]  
    > To complete this step, the user needs **Workspace Owner** permissions and additional access to the Azure subscription and Resource Group. For more information, see [prerequisites](/sccm/desktop-analytics/overview#prerequisites).  

    - To use an existing workspace for Desktop Analytics, select it, and continue with the next step.  

        > [!Note]  
        > If you're already using Windows Analytics, select that same workspace. You need to reenroll devices to Desktop Analytics that you previously enrolled in Windows Analytics.
        >
        > You can only have one Desktop Analytics workspace per Azure AD tenant. Devices can only send diagnostic data to one workspace.  

    - To create a workspace for Desktop Analytics, select **Add workspace**.  

        1. Enter a **Workspace name**.<!--do we have any guidance for this name?-->  

        2. Select the drop-down list to **Select the Azure subscription name for this workspace**, and choose the Azure subscription for this workspace.  

        3. **Create new** Resource group or **Use existing**.

        4. Select the **Region** from the list, and then select **Add**.  

6. Select a new or existing workspace, and then select **Set as Desktop Analytics workspace**.  Then select **Continue** in the **Confirm and grant access** dialog.  

7. In the new browser tab, pick an account to use to sign in. Select the option to **Consent on behalf of your organization** and select **Accept**.  

    > [!Note]  
    > This consent is to assign the MALogAnalyticsReader application the Log Analytics Reader role for the workspace. This application role is required by Desktop Analytics. For more information, see [MALogAnalyticsReader application role](/sccm/desktop-analytics/troubleshooting#bkmk_MALogAnalyticsReader).  

8. Back on the page to **Set up your workspace**, select **Next**.  

9. On the **Last steps** page, select **Go to Desktop Analytics**.

The Azure portal shows the Desktop Analytics **Home** page.


## Next steps

Advance to the next article to connect Configuration Manager with Desktop Analytics.
> [!div class="nextstepaction"]  
> [Connect Configuration Manager](/sccm/desktop-analytics/connect-configmgr)  
