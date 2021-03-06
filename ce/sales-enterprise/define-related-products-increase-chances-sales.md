---
title: "Define related products to increase sales (Dynamics 365 for Sales) | MicrosoftDocs"
ms.custom: ""
ms.date: 08/31/2017
ms.reviewer: ""
ms.service: "crm-online"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
applies_to: 
  - "Dynamics 365 (online)"
  - "Dynamics 365 Version 9.x"
author: "shubhadaj"
ms.assetid: feff6902-ef54-47ff-a13f-e5edc213adb0
caps.latest.revision: 18
ms.author: "shujoshi"
manager: "brycho"
---
# Define related products to increase sales (Sales)

[!INCLUDE[cc-applies-to-update-9-0-0](../includes/cc_applies_to_update_9_0_0.md)]

Improve your opportunities to increase sales by adding related products as suggestions for up-sell, cross-sell, accessories, or substitutes. Defining related products will help your sales agents with their recommendations to customers. You can add related products to a product or product bundle, but not to product families.  
  
 The related products are displayed as suggestions to your sales agents during opportunity or order management. These suggestions help your sales agents recommend related products and bundles/kits to the customers, and increase product sales. You can define the following relationships for a product: Accessory, cross-sell, substitute, and up-sell. For example, for a [!INCLUDE[pn_microsoft_surface](../includes/pn-microsoft-surface.md)] Pro product, you can add [!INCLUDE[pn_microsoft_surface](../includes/pn-microsoft-surface.md)] Book as an up-sell product so that when your sales agent is adding [!INCLUDE[pn_microsoft_surface](../includes/pn-microsoft-surface.md)] Pro to any opportunity, quote, order, or invoice,  [!INCLUDE[pn_microsoft_surface](../includes/pn-microsoft-surface.md)] is suggested as the up-sell option.  
  
1. [!INCLUDE[proc_settings_prod_catalog](../includes/proc-settings-prod-catalog.md)]  
  
2.  Click **Families & Product**.  
  
3.  Open a product you want to define related products for. The product must be in the **Draft**, **Active** or **Under Revision** state.  
  
4.  In the **Product Relationships** section, click the **Add Product Relationship** button ![Add a record button](../sales-enterprise/media/add-recordbutton.gif "Add a record button").  
  
5.  In the quick form, enter the following details:  
  
    - **Related Product**. Select a product that you want to add as a related product to the existing product record you're working on.  
  
    - **Sales Relation Type**. Select whether you want to add the product as an up-sell, cross-sell, accessory, or substitute product.  
  
    - **Direction**. Select whether the relationship between the products will be uni-directional or bi-directional. When you select **Uni-Directional**, the product that you select in **Related Product** will be shown as a recommendation for the existing product but not vice-versa.  
  
6.  Click **Save**.  
  
 When you add a product to an opportunity, the sales agents can see the related product as suggestions for an opportunity. The **Suggestions** dialog box on the opportunity record suggests only those products that are related to the main product and have the same price list as the one associated with the opportunity.  
  
 ![Product suggestions an opportunity in Dynamics 365](../sales-enterprise/media/v7-product-suggestions.png "Product suggestions an opportunity in Dynamics 365 for Sales")  
  
## Typical next steps  
 ![Right arrow button](../sales-enterprise/media/walkthrough-orange-right-arrow.png "Right arrow button") [Publish a product or bundle to make it available for selling](../sales-enterprise/publish-product-bundle-make-available-selling.md)  
  
 ![Home button](../sales-enterprise/media/walkthrough-home.png "Home button") [Set up a product catalog: Walkthrough](../sales-enterprise/set-up-product-catalog-walkthrough.md)  
  
### See also  
 [Create a product family](../sales-enterprise/create-product-family.md)
