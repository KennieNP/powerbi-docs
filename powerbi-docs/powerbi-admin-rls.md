---
title: Row-level security (RLS) with Power BI
description: How to configure row-level security for imported datasets, and DirectQuery, within the Power BI service.
services: powerbi
documentationcenter: ''
author: guyinacube
manager: erikre
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''

ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 08/11/2017
ms.author: asaxton

---
# Row-level security (RLS) with Power BI
<iframe width="560" height="315" src="https://www.youtube.com/embed/67fK0GoVQ80?showinfo=0" frameborder="0" allowfullscreen></iframe>

Row-level security (RLS) with Power BI can be used to restrict data access for given users. Filters restrict data at the row level. You can define filters within roles.

You can configure RLS for data models imported into Power BI with Power BI Desktop. You can also configure RLS on datasets that are using DirectQuery, such as SQL Server. Previously, you were only able to implement RLS within on-premises Analysis Services models outside of Power BI. For Analysis Services live connections, you configure Row-level security on the on-premises model. The security option will not show up for live connection datasets.

[!INCLUDE [include-short-name](includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](includes/rls-desktop-view-as-roles.md)]

## Manage security on your model
To manage security on your data model, you will want to do the following.

1. Select the **ellipse (…)** for a dataset.
2. Select **Security**.
   
   ![](media/powerbi-admin-rls/rls-security.png)

This will take you to the RLS page for you to add members to a role you created in Power BI Desktop. Only the owners of the dataset will see Security available. If the dataset is in a Group, only Administrators of the group will see the security option. 

You can only create or modify roles within Power BI Desktop.

## Working with members
### Add members
You can add a member to the role by typing in the email address, or name, of the user, security group or distribution list you want to add. This member has to be within your organization. You cannot add Groups created within Power BI.

![](media/powerbi-admin-rls/rls-add-member.png)

You can also see how many members are part of the role by the number in parenthesis next to the role name, or next to Members.

![](media/powerbi-admin-rls/rls-member-count.png)

### Remove members
You can remove members by selecting the X next to their name. 

![](media/powerbi-admin-rls/rls-remove-member.png)

## Validating the role within the Power BI service
You can validate that the role you defined is working correctly by testing the role. 

1. Select the **ellipsis (...)** next to the role.
2. Select **Test data as role**

![](media/powerbi-admin-rls/rls-test-role.png)

You will then see reports that are available for this role. Dashboards are not presented in this view. In the blue bar above, you will see what is being applied.

![](media/powerbi-admin-rls/rls-test-role2.png)

You can test other roles, or combination of roles, by selecting **Now viewing as**.

![](media/powerbi-admin-rls/rls-test-role3.png)

You can choose to view data as a specific person, or you can select a combination of available roles to validate they are working. 

To return to normal viewing, select **Back to Row-Level Security**.

[!INCLUDE [include-short-name](includes/rls-usernames.md)]

## Using RLS with app workspaces in Power BI
If you publish your Power BI Desktop report to an app workspace within the Power BI service, the roles will be applied to read-only members. You will need to indicate that members can only view Power BI content within the app workspace settings.

> [!WARNING]
> If you have configured the app workspace so that members have edit permissions, the RLS roles will not be applied to them. Users will be able to see all of the data.
> 
> 

![](media/powerbi-admin-rls/rls-group-settings.png)

[!INCLUDE [include-short-name](includes/rls-limitations.md)]

[!INCLUDE [include-short-name](includes/rls-faq.md)]

## Next steps
[Row-level security (RLS) with Power BI Desktop](powerbi-desktop-rls.md)  

More questions? [Try asking the Power BI Community](http://community.powerbi.com/)
