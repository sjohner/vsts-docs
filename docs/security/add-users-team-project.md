---
title: Add users to a team or team project
description: Quickstart guide to add users to a group, team project, or team 
ms.assetid: 3cfefdd2-b161-4e04-8dc0-e2deeac50262
ms.prod: vs-devops-alm
ms.technology: vs-devops-tfs
ms.manager: douge
ms.author: kaelli
ms.topic: get-started-article
ms.date: 10/10/2017
---

# Add users to a team project or specific team  

[!INCLUDE [temp](../_shared/version-vsts-tfs-all-versions.md)]

For anyone to access a team project, they must be added to one of the default security groups or a custom group. Usually you add them to the Contributors group. For a quick look at what permissions are assigned to the default groups, see [Permissions and access](permissions-access.md).

The easiest way to add a number of users to a team project is to add groups defined in [Azure Active Directory (AAD) for VSTS](../accounts/access-with-azure-ad.md) or [Active Directory (AD) for on-premises TFS](../tfs-server/admin/setup-ad-groups.md). 

Once users have been added to a team project, you can browse for that name by display name as well as account name. Also, you can [add them to a specific team](#add-team-members). To add a team, see [Add a team](../work/scale/multiple-teams.md).

<a name="add-users-team-project"></a>
## Add users to a team project

If you don't have a team project yet, create one in [VSTS](../user-guide/sign-up-invite-teammates.md) or set one up in an [on-premises TFS](../accounts/create-team-project.md).

0. Open the web portal and choose the team project where you want to add users or groups. Click the ![gear icon](../_img/icons/gear-icon.png) gear icon to open the administrative context. 
 
	<img src="_img/add-users/choose-team-project-click-gear-icon.png" alt="VSTS, TFS 2017, Team Project hub, Click gear icon to open the Admin context" style="border: 2px solid #C3C3C3;" /> 
<!---
**TFS 2015**
    ![Select team project from TFS home page](_img/add-users-team-project/overview.png)
-->

0. Open the **Security** page and under the **Groups** section, choose one of the following:
    -   To add users who will require read-only access to the project, choose **Readers**.
    -   To add users who will contribute fully to this project or who have been granted stakeholder access, choose **Contributors**.
    -   For users who will need to administrate the project, choose **Project Administrators**. To learn more, see  [Set permissions at the project-level or project collection-level](set-project-collection-level-permissions.md). 

0. Next, click the **Members** tab. 

	Here we choose the Contributors group.  

	<img src="_img/add-users/add-members-to-contributors-group.png" alt="Admin context, Security page, Contributors group, Membership page" style="border: 2px solid #C3C3C3;" /> 

    > [!TIP]  
    > Managing users is much easier [using groups](../security/about-permissions.md), not individual users.

	By default, the default team group and all other teams you add to the team project are included as members of the Contributors group. So, you can choose to add a new user as a member of a team instead, and the user would automatically inherit Contributor permissions. 

0. Click ![gear icon](../_img/icons/add-light-icon.png)**Add** to add a user or a user group.

0. Type the name of the user account into the text box. You can type several identities into the text box, separated by commas. The system will automatically search for matches. Click the match(es) that meets your choice. 

	<img src="_img/project-level-permissions-add-a-user.png" alt="Add users and group dialog" style="border: 2px solid #C3C3C3;" /> 

	> [!NOTE]   
	> The first time you add a user or group to TFS,
	> you can't browse to it or check the friendly name.
	> After the identity has been added once in TFS, you can just type the friendly name.

<!---**TFS 2015**
    ![Choose the team project group and add members](../accounts/_img/add-users-team-project/add-contributor.png)
3.  In **Identities**, specify the name of the user or group you want to add.
-->
0.  Depending on the user, you might want to customize their permissions for other functionality in the project,
such as [areas and iterations](set-permissions-access-work-tracking.md) or [shared queries](../work/track/set-query-permissions.md).

	> [!NOTE]   
	> Users that have limited access, such as Stakeholders, won't be able to access select features even if granted permissions to those features. To learn more, see [Permissions and access](permissions-access.md).


<a id="add-team-members"> </a>  

## Add users to a team  

Several Agile tools, like capacity planning and team alerts, and dashboard widgets are team-scoped. That is, they automatically reference the user accounts of team members to support planning activities or sending alerts. To learn more, see [About teams and Agile tools](../teams/about-teams-and-settings.md).

<a id="add-team-members-team-services" /> 

0. From the team project admin context, open the Overview page, and then click the team you want to add team members to.   

	<img src="_img/add-users/overview-page-select-team.png" alt="Web portal, Overview page, choose team" style="border: 2px solid #C3C3C3;" />

0. Click ![gear icon](../_img/icons/add-light-icon.png)**Add** to add a user or a user group.

2. Enter the sign-in addresses or display name for each account you want to add. Add them one at a time or all at the same time. You can type several identities into the text box, separated by commas.  

	<img src="_img/project-level-permissions-add-a-user.png" alt="Add users and group dialog" style="border: 2px solid #C3C3C3;" /> 

	> [!TIP]    
	> You must enter user and group names one at a time. However, after entering a name, the account is added to the list, and you can type another name in the Identities text box before choosing to save your changes.  
 
3. To remove members, return to this page, highlight the user name and click **Remove**.  

	<img src="_img/add-users/team-page-remove-team-member.png" alt="Web portal, team admin context, remove a team member" style="border: 2px solid #C3C3C3;" /> 

4. To add an account as a team administrator, click **Add** located in the Team Profile page. For details, see [Add a team administrator](../work/scale/add-team-administrator.md).

## Add users or groups to an access level (TFS only)

For on-premises TFS, you may need to set the access level for a user or group, particularly if those groups don't belong to the default access level. To learn more, see [Change access levels](change-access-levels.md). 

## Add users or groups to Sharepoint or SQL Server Reports (TFS only)

If your TFS deployment is integrated with a SharePoint product or SQL Server Reports, you'll need to manage membership for those products separately from their websites. 

-  [Set SharePoint site permissions](../security/set-sharepoint-permissions.md) 
-  [Grant permissions to view or create SQL Server reports in TFS](../report/admin/grant-permissions-to-reports.md). 

<!---
## Verify

1.  Open the web portal in administration mode and choose **Control Panel**
to navigate to the top-level administration context.

2.  Choose the **Access levels** tab.

3.  Choose the name of each license group in turn, and review the following information:

    -   Which licensing group is set as the default group for the deployment.
	That group name will be followed by **(Default)**.
	This is the group that all users of your deployment of Team Foundation Server will be assigned to by default.

    -   Whether the user for whom you are determining licensing levels is a member
	of a different licensing group than the default group.
	If so, review the description of the features of that licensing group to better understand
	what features are and are not available to that user.

4.  To review the licensing group membership of all users in the deployment at once, choose **Export Audit Log**.
The membership information will be exported to a comma-delimited file.
Save or open the file.
-->


## Try this next

> [!div class="nextstepaction"]
> [Add administrators or set permissions at the project or collection level](set-project-collection-level-permissions.md) 

You can also control access to projects, version control, build, and work items;
learn how from these topics: 

- [Set Git or TFVC repository permissions](set-git-tfvc-repository-permissions.md)
- [Set Git branch permissions](../git/branch-permissions.md)
- [Set build and release permissions](set-build-release-permissions.md)
- [Set permissions and access for work tracking](set-permissions-access-work-tracking.md) 
 
To view permissions for yourself or another user, see [View permissions](../security/view-permissions.md).  




