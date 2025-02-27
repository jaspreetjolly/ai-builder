---
title: Overview of AI Builder in Power Apps - AI Builder | Microsoft Docs
description: Provides an overview of the AI Builder components that are available to use with canvas and model-driven apps in Power Apps.
author: norliu
ms.topic: overview

ms.date: 11/08/2021
ms.author: norliu
ms.reviewer: v-aangie
---

# AI Builder in Power Apps overview

You can use AI Builder in Microsoft Power Apps in one of two ways, depending on the model you will be using. You can:

- Use AI models in the formula bar, or
- Add AI Builder components

You can now use [Power Fx](#use-power-fx-to-consume-ai-models-in-power-apps-preview) expressions to consume AI Builder models in Power Apps. This feature is available in preview.

## Use AI models in the formula bar

You can get support for the following AI Builder models that use Power Apps through the formula bar:

|Model type | Build type  |
|---------|---------|
|[Sentiment analysis](formula-bar.md#sentiment-analysis)  | Prebuilt     |
|[Entity extraction](formula-bar.md#entity-extraction) | Prebuilt and Custom  |
|[Key phrase extraction](formula-bar.md#key-phrase-extraction)   | Prebuilt        |
|[Language detection](formula-bar.md#language-detection)   | Prebuilt     |
|[Category classification](formula-bar.md#category-classification)  | Prebuilt and Custom   |

To learn more about these models, see [Use formulas for text AI models](formula-bar.md).

## Add AI Builder components

AI Builder provides two kinds of Power Apps components. Choose your component based on the models you want to use.

- Components that use prebuilt AI models that are ready to use right away:
  - [Business card reader (canvas app)](business-card-reader-component-in-powerapps.md)
  - [Business card reader (model-driven app)](business-card-reader-component-model-driven.md)
  - [Receipt processor (canvas app)](prebuilt-receipt-processor-component-in-powerapps.md)
  - [Text recognizer (canvas app)](prebuilt-text-recognizer-component-in-powerapps.md)

   For more information on canvas apps, see [What are canvas apps in Power Apps?](/powerapps/maker/canvas-apps/getting-started)

- Components that use custom AI models that you build and train:

  - [Form processor](form-processor-component-in-powerapps.md)
  - [Object detector](object-detector-component-in-powerapps.md)

The AI Builder components for [canvas apps](/powerapps/maker/canvas-apps/getting-started) are available in [Power Apps Studio](/powerapps/teams/understand-power-apps-studio) and appear on the **Insert** tab when you build your canvas app.

> [!div class="mx-imgBorder"]
> ![Power Apps Studio.](media/canvas-studio.png "Power Apps Studio")

## Use Power Fx to consume AI models in Power Apps (preview)

The easiest, most versatile way you can build expressions for AI Builder models in Power Apps is with [Power Fx](powerfx-in-powerapps.md). This is the low-code formula language that works much like Excel. Power Fx in Power Apps supports all prebuilt and custom AI models. It also supports models built on the Microsoft Azure Machine Learning platform.

To learn more, go to [Use Power Fx in AI Builder models in Power Apps (preview)](powerfx-in-powerapps.md).

## Property name changes in AI Builder components for canvas apps

With the [AI Builder component improvements](https://powerapps.microsoft.com/blog/ai-builder-february-update/) released in April 2020, some of the property names in the AI Builder components for canvas apps have changed. In most cases, your existing apps will be automatically updated to use the new property names without any action required from you. However, in cases where the automatic updates to your app are unsuccessful, here are the property name changes you must make in your apps:

- For the [form processor](form-processor-component-in-powerapps.md) component:

    |Previous property name | New property name |
    |:-------|:-------|
    |{Control Name}.FormContent.Fields |{Control Name}.Fields |
    |{Control Name}.FormContent.Tables |{Control Name}.Tables |


- For the [text recognizer](prebuilt-text-recognizer-component-in-powerapps.md) component:

    |Previous property name | New property name |
    |:-------|:-------|
    |{Control Name}.SelectedText |{Control Name}.Selected.Text |
    |{Control Name}.OcrObjects.text |{Control Name}.Results.Text |

- For the [object detector](object-detector-component-in-powerapps.md) component:

    |Previous property name | New property name |
    |:-------|:-------|
    |{Control Name}.VisionObjects.id |{Control Name}.GroupedResults.TagId |
    |{Control Name}.VisionObjects.displayName |{Control Name}.GroupedResults.TagName |
    |{Control Name}.VisionObjects.count |{Control Name}.GroupedResults.ObjectCount |

If your app uses a **data table** component to display results from the **object detector** component, and you don't see the content after this update:

1. Remove the **data table** component from your app.

1. Add it again.

1. Reset the item's property to correctly display the content from the **object detector** component.

### See also

[Feature availability by region](availability-region.md)  
[AI Builder in Power Automate](use-in-flow-overview.md)  
[What are canvas apps?](/powerapps/maker/canvas-apps/getting-started)  
[What are model-driven apps?](/powerapps/maker/model-driven-apps/model-driven-app-overview)


[!INCLUDE[footer-include](includes/footer-banner.md)]