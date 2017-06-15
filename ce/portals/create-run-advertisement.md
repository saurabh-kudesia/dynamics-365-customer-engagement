---
title: "Create and run advertisements on a portal in Dynamics 365 | MicrosoftDocs"
description: ""
ms.custom: ""
ms.date: 05/22/2017
ms.service: crm-online
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: article
ms.assetid: c297e1d7-14c4-4545-8c3c-f2de3db8fa38
ms.reviewer: ""
author: sbmjais
ms.author: shjais
manager: sakudes
---
# Create and run advertisements on a portal
[comment]: <> (Add cross-ref to ad entity attribute table)
Create text or image-based ads and have them run in multiple placements throughout your site. Randomize ads or select specific ads for specific placements. You can choose release and expiration dates for time-sensitive, scheduled content. Ads can be hyperlinked to any destination and open in the current window or a new window. Advertisements are displayed in the portal via two [!INCLUDE[pn-dynamics-crm](../includes/pn-dynamics-crm.md)] entities: The Ad Placement entity and associated Ad entity. Ads can be surfaced in many ways: with pre-made Liquid Templates available within the [!INCLUDE[pn-dynamics-crm](../includes/pn-dynamics-crm.md)] portals application via Liquid Templating/example Web Templates, or within the.aspx page via MVC actions.

## Create a new advertisement

Ads represent the specific advertisement or image that will appear on the portal at a given time. The Ad entity will be displayed in the location specified by the Ad placement. The Ad must be associated with an Ad Placement to appear on the portal. For this demonstration, the out-of-the-box example "Place Holder" Ad and "Sidebar Bottom" Ad Placement will be surfaced in the Company Portal to exhibit basic functionality and to help you gain familiarity prior to creating more complex Ads. Any of the starter sites can be used in place of the Company Portal. However, note that the Liquid Templates used for this demonstration calls on the "Sidebar Bottom" Ad Placement name.

1. Navigate to **Portals** then **Ads**
2. Open the **Placeholder** Ad associated with the **Company Portal** website (this can be done with starter site of your choosing by clicking **+NEW** and creating an identical Ad sub the Website). 
3. Click the **Save** icon in the lower right corner (or **Save & Close** in the upper left corner if you have created a new ad)

Within the Ad Form you specify a **Name** to describe the Ad, the **Website** where the Ad will be displayed, and a **Publishing State**. Optionally you can specify a Web Template and Release/Expiration date. You must provide some sort of data for the Ad to be displayed. Use the Ad entity attribute table later in this guide to craft the specifics of your ad.


## Create a new advertisement placements

1. Navigate to **Portals** then **Ad Placements**
2. Click the Web Template Field to select a Web Template. For demonstration purposes the "Random Ad" Web Template was chosen.
3. On the right corner of the Ads grid click**+** to select the Ad created in the previous step.
4. Click the **Save** icon in the lower right corner

When creating a new Ad Placement, specify a **Name** to describe the Ad Placement and the **Website** where the Ad Placement will be displayed as required. The example Web Templates that enable use of Ads as an out-of-the-box feature will be displayed within the lookup of the Web Template field in the Form. These templates are also intended to be used as a source to create custom templates.

![See lookup record](media/see-lookup-record.png "See lookup record")  

![Sidebar bottom settings](media/set-sidebar-bottom.png "Sidebar bottom settings")  

![Ad company portal](media/ad-company-portal.png "Ad company portal")  

> [!NOTE] 
> The Ad created above will not be displayed on the home page of the starter portal.

## Using Liquid templates to place advertisements

Content managers may use Liquid to add an Ad to any editable content area, as described in [Add dynamic content and create custom templates](custom-templates-dynamic-content.md) and, more specifically, [Ads](#ads-1).

This template renders an Ad by name, or a random Ad from an Ad Placement. Currently, the code below will not render multiple Ads in the Ad Placement (that is, a rotating ad). To render multiple Ads in the Ad Placement, you would need to build a Liquid Ads API. For more information about built-in web templates, see [Store source content by using web templates](store-content-web-templates.md).

```
{% include 'ad' ad_name:'Name' %}
{% include 'ad' ad_placement_name:'Placement Name' %}
1. {% include 'Random Ad' placement:ads.placements["Sidebar Bottom"] %}
```
OR 

```
1. {% include 'Ad Template' ad:ads{"Retail Ad - Go Greene"] %}
```



## Attributes

The Ad Entity has the following attributes:

| Name               | Description                                                                                                                                                                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Name               | A descriptive name for the Ad                                                                                                                                                                                                                                                                                                                          |
| Website            | The associated Website Required.                                                                                                                                                                                                                                                                                                                       |
| Web Template       | The associated [web templates](store-content-web-templates.md) that will be used by default to render the Ad. This field is optional; if it is blank the Ad will be rendered using a default template.                                                                                                                                   |  
| Release Date       | Controls a date/time after which the Ad will be visible on the portal. If the Ad Placement is rotating through multiple ads, an unreleased ad will not show. If no released ads are associated with an Ad Placement, nothing will appear. This is useful for controlling the release of time-sensitive content.                                        |
| Expiration Date    | Controls a date/time prior to which the Ad will be visible on the portal.                                                                                                                                                                                                                                                                              |
| Publishing State   | The current Publishing State.                                                                                                                                                                                                                                                                                                                          |
| Redirect URL       | When the Ad is clicked, the user will navigate to this URL.**This field is optional.** If no value is given, the Ad will not be clickable.                                                                                                                                                                                                            |
| Open In New Window | Boolean. If set to true, the Ad will open a new browser window when clicked.                                                                                                                                                                                                                                                                           |
| Title              | A single line of text for the ad which can be displayed on the portal. Whether it is displayed is determined by a property on the AdPlacement control. This is primary useful for text-based ads or simple one-line links that you want to place on the portal by using Ad Placements. If the title is displayed, by default it will be rendered as a hyperlink which points to the Redirect URL. This behavior may be altered by using a custom [web template](store-content-web-templates.md). |                                                                                                                             |  
| Copy               | A multiline body of text or other web content that will be displayed in the ad placement. This allows the placement to be used in a similar way to content snippets, but it is best to avoid using them to serve simply as a bucket to hold content (use snippets for that). Instead, they are best used to display rotating image or textual content. |
| Image URL          | The URL of the image which will be displayed by the ad. Optional; Use this field if you want the Ad to render a static resource or a web file. The Image will be clickable and link to the redirect URL, if one is given. If an Ad has a note attached to it with an image file attachment, the Ad will render that as its image. This is possibly the most convenient way to set up images for ads, and ties the image directly with the Ad. In this case, Using the Image URL field is not necessary. |                                                                       |
| Image width        | Width of the image. This field is not required but is recommended to ensure that the rendered Ad is valid and accessible HTML                                                                                                                                                                                                                                               |
| Image Height       | Height of the image. This field is not required but is recommended to ensure that the rendered Ad is valid and accessible HTML                                                                                                                                                                                                                                               |
| Image Alt Text     | Alt Text for the image. This field is not required but is recommended to ensure that the rendered Ad is valid and accessible HTML.|


### See Also

[Configure a [!INCLUDE[pn-dynamics-crm](../includes/pn-dynamics-crm.md)] portal](configure-portal.md)  
[Add a webpage to render a list of records](add-webpage-render-list-records.md)  
[Create and run advertisements on a portal](create-run-advertisement.md)  
[Gather feedback by using polls on a portal](gather-feedback-poll.md)  
[Rate or vote on a webpage or blog post on a portal](rate-webpage-blog-post.md)  
[Redirect to a new URL on a portal](add-redirect-url.md)  
