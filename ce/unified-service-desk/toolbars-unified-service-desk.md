---
title: "Toolbars in Unified Service Desk for Dynamics 365 Customer Engagement| MicrosoftDocs"
description: "Learn about configuring toolbars in Unified Service Desk."
ms.custom: ""
ms.date: 08/23/2017
ms.reviewer: ""
ms.service: "usd"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
applies_to: 
  - "Dynamics 365 (online)"
  - "Dynamics 365 (on-premises)"
  - "Dynamics CRM 2013"
  - "Dynamics CRM 2015"
  - "Dynamics CRM 2016"
ms.assetid: f3738bca-89b7-48e6-bc97-2fb477d727b3
caps.latest.revision: 6
author: "KumarVivek"
ms.author: "kvivek"
manager: "jdaly"
---
# Toolbars in Unified Service Desk
Toolbars in [!INCLUDE[pn_unified_service_desk_for_crm](../includes/pn-unified-service-desk-for-crm.md)] hold and display a list of buttons with images and text. Clicking or tapping the buttons can execute one or more actions.  
  
 Here is the **Main** toolbar in one of the [!INCLUDE[pn_unified_service_desk](../includes/pn-unified-service-desk.md)] sample applications.  
  
 ![Main toolbar in Unified Service Desk](../unified-service-desk/media/usd-toolbar-example.png "Main toolbar in Unified Service Desk")  
  
 You configure toolbars in [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)] in the **Settings** > **Unified Service Desk** > **Toolbars** area. Furthermore, each toolbar is attached to a **Toolbar Container** type of hosted control, which in turn is attached to a display area (panel) in [!INCLUDE[pn_unified_service_desk](../includes/pn-unified-service-desk.md)]. This is done to specify the panel where the toolbar will display in the client application.  
  
 The following image shows the existing toolbars in a [!INCLUDE[pn_unified_service_desk](../includes/pn-unified-service-desk.md)] sample application.  
  
 ![Toolbars in Unified Service Desk](../unified-service-desk/media/usd-toolbars.png "Toolbars in Unified Service Desk")  
  
## Understanding components in a toolbar  
 Click any toolbar name under the **Name** column to view the buttons inside the toolbar, action calls for each button, and the toolbar container that the toolbar is attached to.  
  
 For an example of how to do this, click **Main** on the toolbars page.  
  
- **Toolbar buttons**: The toolbar page displays the buttons in the **Main** toolbar. The order of the buttons determines the placement of buttons from left to right in an ascending order. You can add, remove, or edit an existing button. 
  
 ![Buttons in the main toolbar](../unified-service-desk/media/usd-main-toolbar-buttons.png "Buttons in the main toolbar")  
  
- **Properties of a toolbar button**: To view the properties of a button, such as name, image, button label, tooltip, shortcut key, and action calls associated with a button, click any of the button names. For example, clicking **Dashboard** displays the following information for the button.  
  
 ![Toolbar button properties](../unified-service-desk/media/usd-toolbar-button-properties.png "Toolbar button properties")  
  
- **Toolbar Container**: To view the toolbar container hosted control associated with the **Main** toolbar, click the down arrow next to the **Main** toolbar on the nav bar, and select **Hosted Controls**.  
  
 ![View the toolbar container](../unified-service-desk/media/usd-main-toolbar.png "View the toolbar container")  
  
     The name of the toolbar container attached to the **Main** toolbar is displayed.  
  
 ![Toolbar Container for the Main toolbar](../unified-service-desk/media/usd-main-toolbar-hosted-control.png "Toolbar Container for the Main toolbar")  
  
### See also  
 [Configure toolbars in your application](../unified-service-desk/configure-toolbars-application.md)   
 [Walkthrough 2: Display an external webpage in your agent application](../unified-service-desk/walkthrough-2-display-an-external-webpage-in-your-agent-application.md)   
 [Walkthrough 3: Display Microsoft Dynamics 365 records in your agent application](../unified-service-desk/walkthrough-3-display-microsoft-dynamics-365-records-in-your-agent-application.md)