---
title: "Create a business process flow (Dynamics 365 Customer Engagement)| MicrosoftDocs"
ms.custom: ""
ms.date: 01/17/2018
ms.reviewer: ""
ms.service: "crm-online"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
applies_to: 
  - "Dynamics 365 (online)"
  - "Dynamics 365 Version 9.x"
ms.assetid: efe86ab3-430f-485a-b924-6ed82cfbb449
caps.latest.revision: 39
author: "rdubois"
ms.author: "rdubois"
manager: "brycho"
---
# Create a business process flow to standardize processes

[!INCLUDE[cc-applies-to-update-9-0-0](../includes/cc_applies_to_update_9_0_0.md)]

This topic shows how to create a business process flow with [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] Customer Engagement. To learn more about why you use business process flows, see [Business process flows overview](../customize/business-process-flows-overview.md). For information on creating a mobile task flow, see [Create a mobile task flow](../customize/create-mobile-task-flow.md).  
  
 When a user starts a business process flow, the stages and steps of the process are displayed in the process bar at the top of a form:  
  
 ![Business process with stages](../customize/media/business-process-stages.png "Business process with stages")  
  
 [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] comes with several ready-to-use business process flows for common business scenarios. Add them to your system and use as is, or modify them to fit your business needs. To find out how to add ready-to-use business process flows, see [Add ready-to-use business processes](../customize/add-ready-use-business-processes.md).  
  
<a name="BKMK_Createbusinessprocessflows"></a>   
## Create a business process flow  
  
1. [!INCLUDE[proc_permissions_system_admin_and_customizer](../includes/proc-permissions-system-admin-and-customizer.md)]  
  
    > [!TIP]
    >  In [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)], after you create a business process flow definition, you can provide control over who can create, read, update, or delete the business process flow instance. For example, for service-related processes, you could provide full access for customer service reps to change the business process flow instance, but provide read-only access to the instance for sales reps so they can monitor post-sales activities for their customers. To set security for a business process flow definition you create, click **Enable Security Roles** on the action bar.  
  
    #### Check your security role  
  
    1. [!INCLUDE[proc_follow_steps_in_link](../includes/proc-follow-steps-in-link.md)]  
  
    2. [!INCLUDE[proc_dont_have_correct_permissions](../includes/proc-dont-have-correct-permissions.md)]  
  
2. [!INCLUDE[proc_settings_processes](../includes/proc-settings-processes.md)]  
  
3.  On the **Actions** toolbar, click **New**.  
  
4.  In the **Create Process**  dialog box, complete the required fields:  
  
    -   Enter a process name. The name of the process doesn’t need to be unique, but it should be meaningful for people who need to choose a process. You can change this later.  
  
    -   In the **Category** list, select **Business Process Flow**.  
  
         You cannot change the category after you create the process.  
  
    -   In the **Entity** list, select the entity you want to base the process on.  
  
         The entity you select affects the fields available for steps that can be added to the first stage of the process flow. If you don’t find the entity you want, make sure the entity has the Business process flows (fields will be created) option set in the entity definition. You cannot change this after you save the process.  
  
5. [!INCLUDE[proc_click_or_tap_ok](../includes/proc-click-or-tap-ok.md)]  
  
     The new process is created, and the business process flow designer opens with a single stage already created for you.  
  
 ![Business process flow window showing main elements](../customize/media/business-process-flow-window-showing-main-elements.png "Business process flow window showing main elements")  
  
6. **Add stages.** If your users will progress from one business stage to another in the  process:  
  
    1.  Drag a **Stage** component from the **Components** tab and drop it on a + sign in the designer.  
  
        ![Drag a business process stage](../customize/media/drag-business-process-stage.png "Drag a business process stage")  
  
    2.  To set the properties for a stage, click the stage, and then set the properties in the **Properties** tab on the right side of the screen:  
  
        -   Enter a display name.  
  
        -   If desired, select a category for the stage.  The category  (such as **Qualify** or **Develop**) appears as a chevron in the process bar.  
  
            ![Business process bar chevron](../customize/media/business-process-bar-chevron.png "Business process bar chevron")  
  
        -   When you're done changing properties, click the **Apply** button.  
  
7. **Add steps to a stage.** To see the steps in a stage, click **Details** in the lower-right corner of the stage. To add more steps:  
  
    1.  Drag the **Step** component to the stage from the **Components** tab.  
  
        ![Add step to a stage in a business process](../customize/media/add-step-stage-business-process.png "Add step to a stage in a business process")  
  
    2.  Click the step, and then set properties in the **Properties** tab:  
  
        1.  Enter a display name for the step.  
  
        2.  If you want users to enter data to complete a step, select the appropriate field from the drop-down list.  
  
        3.  Select **Required** if people must fill in the field to complete the step before moving to the next stage of the process.  
  
        4.  Click **Apply** when you're done.  
  
8. **Add a branch (condition) to the process.** To add a branching condition:  
  
    1.  Drag the **Condition** component from the **Components** tab to a + sign between two stages.  
  
        ![Add a Condition to a business process flow](../customize/media/add-condition-business-process-flow.png "Add a Condition to a business process flow")  
  
    2.  Click the condition, and then set properties in the **Properties** tab. For more information on branching properties, see [Enhance business process flows with branching](../customize/enhance-business-process-flows-branching.md). When you're finished setting properties for the condition, click **Apply**.  
  
9. **Add a workflow.** To invoke a workflow:  
  
    1.  Drag a **Workflow** component from the **Components** tab to a stage or to the **Global Workflow** item in the designer.   Which one you add it to depends on the following:  
  
       - **Drag it to a stage** when you want to trigger the workflow on entry or exit of the stage. The workflow component must be based on the same primary entity as the stage.  
  
       - **Drag it to the Global Workflow item** when you want to trigger the workflow when the process is activated or when the process is archived (when the status changes to **Completed** or **Abandoned**). The workflow component must be based on the same primary entity as the process.  
  
    2.  Click the workflow, and then set properties in the **Properties** tab:  
  
       1.  Enter a display name.  
  
       2.  Select when the workflow should be triggered.  
  
       3.  Search for an existing on-demand active workflow that matches the stage entity or create a new workflow by clicking **New**.  
  
       4.  Click **Apply** when you're done.  
  
       For more information on workflows, see [Workflow processes](../customize/workflow-processes.md).  
  
10. To validate the business process flow, click **Validate** on the action bar.  
  
11. To save the process as a draft while you continue to work on it, click **Save** in the action bar.  
  
    > [!IMPORTANT]
    >  As long as a process is a draft, people won’t be able to use it.  
  
12. To activate the process and make it available to your team, click **Activate** on the action bar.  
  
> [!TIP] 
>  Here are a few tips to keep in mind as you work on your task flow in the designer window:  
>   
> - To take a snapshot of everything in the business process flow window, click **Snapshot** on the action bar. This is useful, for example, if you want to share and get comments on the process from a team member.  
> - Use the mini-map to navigate quickly to different parts of the process. This is useful when you have a complicated process that scrolls off the screen.  
> - To add a description for the business process, click **Details** under the process name in the left corner of the business process flow window. You can use up to 2000 characters.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## Edit a business process flow  
 To edit business process flows in [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)], [!INCLUDE[proc_settings_processes](../includes/proc-settings-processes.md)], and then select the **Business Process Flows** view.  
  
 ![Business Process Flows view selection](../customize/media/business-process-flows-view.png "Business Process Flows view selection")  
  
 When you click on the name  of the business process flow you want to edit it opens in the designer, where you can make any updates you want. Expand **Details** under the name of the process to rename it or add a description, and view additional information.  
  
 ![Expanded details section of a business process flow](../customize/media/business-process-flow-details.png "Expanded details section of a business process flow")  
  
  
 ## Other things to know about business process flows
 **Edit Stages**  
 Business process flows can have up to 30 stages.    
  
 You can add or change the following properties of a stage:  
  
- **Stage Name**  
  
- **Entity**. You can change the entity for any stage except the first one.  
  
- **Stage Category**. A category lets you group stages by a type of action. It is useful for reports that will group records by the stage they are in. The options for the stage category come from the Stage Category global option set. You can add additional options to this global option set and change the labels of existing options if you want. You can also delete these options if you wish, but we recommend that you keep the existing options. You won’t be able to add the exact same option back if you delete it. If you don’t want them to be used, change the label to ”Do not use”.  
  
- **Relationship**. Enter a relationship when the preceding stage in the process is based on a different entity. For the stage currently being defined, choose **Select relationships** to identify a relationship to use when moving between the two stages. It is recommended you select a relationship for the following benefits:  
  
    -   Relationships often have attribute maps defined that automatically carry over data between records, minimizing data entry.  
  
    -   When you select **Next Stage** on the process bar for a record, any records that use the relationship will be listed in the process flow, thereby promoting reuse of records in the process. In addition, you can use workflows to automate creation of records so that the user simply selects it instead of creating one to further streamline the process.  
  
 **Edit Steps**  
 Each stage can have up to 30 steps.    
  
 **Add branch**  
 To learn about adding a branch to a stage, see [Enhance business process flows with branching](../customize/enhance-business-process-flows-branching.md).  
  
 To make a business process flow available for people to use, you must order the process flow, enable security roles, and activate it.  
  
 **Set Process Flow Order**  
 When you have more than one business process flow for an entity (record type), you’ll need to set which process is automatically assigned to new records.. In the command bar, select **Order Process Flow**. For new records or records that do not already have a process flow associated with them, the first business process flow that a user has access to is the one that will be used.  
  
 **Enable Security Roles**  
 People will only be able to use business process flows that are associated with security roles assigned to their user account. By default, only the **System Administrator** and **System Customizer** security roles can view a new business process flow.  
  
-   To set these roles, in the command bar, select **Enable Security Roles**. You can choose either the **Enable for Everyone** or **Enable only for the selected security roles** options.  
  
-   If you choose **Enable only for the selected security roles**, you can select which security roles will allow access to the business process flow.  
  
 **Activate**  
 Before anyone can use the business process flow, you must activate it. In the command bar, select **Activate**. After you confirm the activation, the business process flow is ready to use. If a business process flow has errors, you will not be able to activate it until the errors are corrected.  

## Preview feature: Add an on-demand action to a business process flow
The [!INCLUDE [pn-crm-9-0-0-online](../includes/pn-crm-9-0-0-online.md)] update introduces a new business process flow feature: business process flow automation with Action Steps. You can add a button to a business process flow that will trigger an action or workflow.

> [!IMPORTANT]
> [!INCLUDE [cc-preview-features-definition](../includes/cc-preview-features-definition.md)]

> [!INCLUDE [cc-preview-features-no-ms-support](../includes/cc-preview-features-no-ms-support.md)]

### Enable Action Step support for business process flows 
[comment]: <> (Shouldn't step 4 be "Select Enable Action Step Support for Business Process Flows Preview"? The radio button is beside this text, not the heading.)
1.	Go to **Settings** > **Administration** > **System Settings**.
2.	Select the **Preview** tab.
3.	Review, and if you agree, accept the license terms.
4.	Select **Action Step Support for Business Process Flows Preview**, and then select **OK**.

    ![Enable business process flow preview feature](media/enable-bpf-actionstep.png)

### Add on-demand workflows or actions using an Action Step
Suppose that, as part of the opportunity qualification process, the Contoso organization requires all opportunities to be reviewed by a designated reviewer. Subsequently, the Contoso organization has an action that: 
[comment]: <> (I don't understand "Subsequently,..."  Did they create the action later? Or does it already exist, as implied by "has?" We should remove "Subsequently," and say that they created the action--or just delete "Subsequently," if the action already exists. Also, we can put the colon right after "that:" we don't need "the following two tasks." The tasks complete the sentence.)
- Creates a task record that is assigned to the opportunity reviewer. 
- Appends “Ready for review” to the opportunity topic. 

Additionally, Contoso needs to be able to run these actions on demand. To integrate these tasks into the opportunity qualification process, the actions must appear on the opportunity business process flow. To enable this functionality, select **As a Business Process Flow action step**.
[comment]: <> (I moved the sentence that talks about running the actions on demand so that it follows the actions we are talking about.)
![Available to run as a business process flow.](../customize/media/action-available-to-run.png)

Next, the Action Step is added to Contoso’s opportunity business process flow. Then the process flow is validated and updated.

![Action added to the opportunity Business Process Flow.](media/add-action-to-bpf.png)

Now, members of Contoso’s salesforce can kick-off the action from the **Opportunity Qualify** business process step, on demand, by selecting **Execute**.

![Execute action.](media/action-execute.png)

> [!IMPORTANT]
> - To be able to execute an action or workflow on demand, the business process flow must include an Action Step. If the Action Step runs a workflow, the workflow must be configured to run on demand.
> - The entity associated with the action or workflow must be the same as the entity associated with the business process flow.

### Limitations of using Action Steps in a business process flow

- Any user customization that uses Action Steps is not supported when importing or exporting solutions.
- Dynamics 365 actions are not available as Action Steps if the input or output parameters are Entity, EntityCollection, or OptionSet (Picklist) types. Actions with more than one EntityReference output parameter or any number of EntityReference input parameters are not available as Action Steps. Actions not associated with a primary entity (global action) are not available as Action Steps.

  
### See also  
 [Business process flows overview](../customize/business-process-flows-overview.md)   
 [Enhance business process flows with branching ](../customize/enhance-business-process-flows-branching.md)</br> 
 [Create a mobile task flow](../customize/create-mobile-task-flow.md)   
 [Add ready-to-use business processes](../customize/add-ready-use-business-processes.md)   
 [Create business rules and recommendations to apply logic in a form](../customize/create-business-rules-recommendations-apply-logic-form.md)   
 [Create custom business logic with processes](../customize/guide-staff-through-common-tasks-processes.md)  
 [Workflow processes](../customize/workflow-processes.md)
