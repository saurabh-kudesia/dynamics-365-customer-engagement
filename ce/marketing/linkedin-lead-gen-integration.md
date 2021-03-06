---
title: "Capture leads generated on LinkedIn (Dynamics 365 for Marketing) | Microsoft Docs "
description: "How to set up and use the connector to LinkedIn Lead Gen Forms, which imports leads from LinkedIn to Dynamics 365 for Marketing"
keywords: "LinkedIn; Lead Gen Forms; lead; connector"
ms.date: 12/15/2017
ms.service: crm-online
ms.topic: article
applies_to:
  - "Dynamics 365 (online)"
  - "Dynamics 365 Version 9.x"
ms.assetid: ec81d712-2c82-4ce0-83c5-ccfbafab71bb
author: kamaybac
ms.author: kamaybac
manager: sakudes
ms.reviewer: renwe
topic-status: Drafting
---

# [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen integration

[!INCLUDE[cc_applies_to_update_9_0_0](../includes/cc_applies_to_update_9_0_0.md)]

[!INCLUDE[cc-beta-prerelease-disclaimer](../includes/cc-beta-prerelease-disclaimer.md)]

 [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)], includes a connector for [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen. Use this feature to see how people are interacting with your marketing initiatives in [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] and to bring leads and lead information generated by using the [LinkedIn Lead Gen](https://business.linkedin.com/marketing-solutions/native-advertising/lead-gen-ads) tools directly into [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)].

To see the information collected by [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen, open a lead and go to its **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Info** tab.

To sync leads from [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] and run campaigns on [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)], you need access to a [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] account that can manage sponsored content by using [LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/56969).

## Enable users to work with the connector and assign security roles to users

The solution creates two new security roles, which you assign to users so they can work with [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen forms in [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)]. A third role, [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen S2S Inbound, is an internal security role used by the solution to sync data.

- **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen Forms Administrator**: Users with this role can configure lead matching strategies, [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] field mapping, and solution settings for [!INCLUDE[cc-linkedin-solution](../includes/cc-linkedin-solution.md)].
- **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen Forms Salesperson**: These users can authorize [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] user profiles to sync data to [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)], and view details about the synced submissions.

Assign these security roles to users you want to provide access to the **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen** menu item. To learn how to assign a security role to users, see [TechNet: Create users and assign Dynamics 365 (online) security roles](https://technet.microsoft.com/library/jj191623.aspx#BKMK_AssignSecurity).

## Configure a matching strategy to update leads from [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen ads

When a new lead is synced from [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)], [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)] can either update an existing lead record if the person is already known, or create a new lead if it's the first contact with this person. New [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] leads appear as **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Form Submissions** in [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)]. The information in [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] form submissions consists of the answers given by [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] members when they submitted the forms.

To match existing leads in [!INCLUDE[pn-crm-online-shortest](../includes/pn-crm-online-shortest.md)] with new [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] form submission answers, users who have at least the **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen Forms Connector Administrator** security role can define a [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] lead matching strategy in [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)]. A matching strategy maps the fields of a [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] form submission to the record fields for a lead in [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)]. By default, a matching strategy based on a lead's email address is activated.

A matching strategy applies to all [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] leads in the same [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)] organization. If a matching strategy contains more than one field mapping, all mappings must match before an existing lead record is updated. We recommend maintaining simple matching strategies—for example, strategies based only on phone number or email address. If only a subset of the fields match, by default [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)] creates a new lead from the form submission.

### Create a [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] lead matching strategy

1. Go to **Marketing** &gt; **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen** &gt; **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Matching Strategies**.

1. To create the matching strategy, select **New**, enter a **Name**, and then select **Save**.

1. To add a [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] field mapping record, select **Add** and enter the name of the [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] member field.

1. Select the **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Field Mapping** record to add it to this matching strategy.

### Activate a different LinkedIn lead matching strategy

1. Go to **Marketing** &gt; **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen** &gt; **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Matching Strategies**.

1. In the list, select the matching strategy that you want to activate.

1. In the **Activate** menu in the matching strategy details, select **Yes**.

1. If another matching strategy is active, it will become deactivated.

### Edit a [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] lead matching strategy

1. Go to **Marketing** &gt; **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen** &gt; **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Matching Strategies**.

1. In the list, select the matching strategy that you want to edit.

1. To add an additional [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] field mapping record, select **Add** and enter the name of the [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] member field.

1. To remove a [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] field mapping record, select **Delete**.

### Delete a [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] lead matching strategy

1. Go to **Marketing** &gt; **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen** &gt; **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Matching Strategies**.

1. Select the check box for the lead matching strategy you want to delete.
    You can't delete the activated lead matching strategy.

1. Select **Delete**, and then confirm your deletion.

## Establish a connection between [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)] Connector for [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen Forms and [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)]

Before we can sync leads from [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] campaign accounts to a [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)] organization, a [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] member with access to [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Campaign Manager is required to authorize their [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] accounts in [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)]. In [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)], this user requires at least a **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen Forms Connector Salesperson** security role.

More information about assigning security roles to users: [TechNet: Create users and assign Dynamics 365 (online) security roles](https://technet.microsoft.com/library/jj191623.aspx)

### Authorize [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)] to sync data from [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Campaign Manager

1. Go to **Marketing** &gt; **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen** &gt; **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] User Profiles**.

1. To add a new [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] user profile record, select **New**, enter a **Name**, and then select **Save**.

1. To add [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] accounts to this user profile, select **Authorize** on the command bar.

1. Enter the credentials for your [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] profile, and then select **Sign In**.

1. In the permissions dialog box, select **Allow**.

1. Check and confirm the [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)] organization you want to sync your [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] data to.

After successful authorization, the associated [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] accounts are listed in the **Associated [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Accounts** section. You can review the details of the [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] accounts in the form. It might take a few seconds to get the accounts; try refreshing the view if you don't see them.

[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] form submissions are now synced automatically to [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)]. You'll be able to see the data in [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)] as soon as the sync is complete, which might take a few minutes. Usually it's not required, but you can trigger an optional, on-demand sync of [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] form submissions after authorizing a profile by selecting **Sync submissions**.

## Analyze leads and lead performance

When a [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] lead matches a lead record in [!INCLUDE[pn-crm-online-shortest](../includes/pn-crm-online-shortest.md)], the lead record is updated with additional information. In addition to the updates of individual lead records, charts on dashboards can represent the performance of a marketing campaign on [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)].

### See the details of a lead

To see the details of a lead record in [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)], go to **Marketing** &gt; **Lead Management** &gt; **Leads** and select the lead record from the list. If the lead was created by [!INCLUDE[cc-linkedin-solution](../includes/cc-linkedin-solution.md)], the lead source is **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Sponsored Content**. If an existing lead record was updated, [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)] updates the lead field values by using the information submitted by the lead on [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)]. [!INCLUDE[proc-more-information](../includes/proc-more-information.md)] [Create or edit a lead](https://go.microsoft.com/fwlink/p?linkid=832163)

> [!NOTE]
> [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] campaigns automatically create a **Customer Journey** record. To stop these records from being automatically generated, a system administrator or customizer needs to edit the **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] LeadGen Integration Configurations** entity and change the value for the **Create Journeys for [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Campaigns** attribute from **Yes** to **No**. For quick access to this custom entity, consider adding it to the site map.


### Review the aggregated lead performance

Work with a dashboard containing charts about the source of new leads, or create new dashboards by using the charts that matter the most to get your reporting completed.

When you create your own dashboard, consider adding a chart for the record type **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Form Submissions** to see how your campaigns perform compared to each other. Or, you can create a **Leads by Source** chart for the record type Lead. Give it a try!

### Analyze individual [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen forms and submissions

To see all form submissions in [!INCLUDE[pn-microsoftcrm](../includes/pn-dynamics-365.md)], go to **Marketing** &gt; **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen** &gt; **[!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Form Submissions**. You can drill down to individual submissions to see the details of the lead and the information provided by the [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] members when they answered the underlying [!INCLUDE[pn-linkedin](../includes/pn-linkedin.md)] Lead Gen form.

### See also

[Manage customer information](manage-customer-information.md)