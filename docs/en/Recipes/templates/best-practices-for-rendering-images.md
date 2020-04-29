---
title: Best practices for rendering images
description: "Learn now all best practices for rendering images in your store's theme and improve the way in which images are cropped, rendered and displayed to end users"
date: "2020-04-29"
tags: ["best-practices", "guidelines", "images", "rendering", "display"]
version: "0.x"
git: "https://github.com/vtex-apps/io-documentation/blob/new-docs-and-fix/docs/en/Recipes/templates/best-practices-for-rendering-images.md"
---

# Best practices for rendering images

When setting up your store's theme, you'll often want to use images for the brand's visual identity.

Among the many options available in Store Framework for the use of images, you can **apply configurations to your theme that directly impact the way in which images are cropped, rendered and displayed to end users**.

We have put together a best practices guide that should be followed in order to have your theme's images displayed in the best possible way and thus avoid performance risks when rendering your store's UI.

## Best practices

### Uploading images to your theme's code
  
Images that are uploaded to your theme's code must always [**use the Assets Builder**](https://vtex.io/docs/recipes/development/using-the-assets-builder) or the admin's Site Editor.

Declaring the URLs of the desired images directly in the theme's code in the `blocks.json` file will prevent the images from matching size when rendered, making the UI's image components deformed due to different dimensions.
  
The Assets Builder, along with the admin's Site Editor, ensures that uploaded images are cropped to size when rendered in the UI, making their presentation consistent and uniform to end users. 

## Choosing the most adequate block

VTEX IO Store Framework has so many different blocks that you can often configure one in your theme that's not the best fit for what you're trying to achieve.   

It's no different with images. With so many blocks responsible for rendering images on the UI, identifying the best suited block can be a challenge. 

Therefore, another best practice is to **understand the main functionality of each image block** and, consequently, be able to **choose the one that best fits your scenario**.
  
The image blocks are:

- **Logo** - Responsible for rendering your brand's logo. It should preferably be used in your store's Header or Footer. The block is exported by the Store Components app. 
- **Infocard** - The Infocard block creates images in the UI which have links and buttons that direct the user's flow. Infocards are recommended in scenarios in which you want to render an image that's specifically tied to a redirect with Call to action buttons/links. This block is also exported by the Store Components app.
- **Rich Text** - The Rich Texts blocks, exported by the Rich Text app, are meant to create markdown texts in your UI. It may be a block that seems simple, but it allows plenty of customization, such as passing an image URL to be rendered. The Rich Text is mainly recommended for building text communications that may need to have an image linked to them.
- **Product Summary Image** - The Product Summary Image block is responsible for displaying the product image usually attached to other product summary informations, such as name and price. This block, exported by the Product Summary, must be displayed within other store components, such as the Shelf. 
- **Image** - The Image block basically renders a image in your store's UI, without links/buttons/markdown texts/product info summary attached to it. It is responsible solely for rendering an image of your choosing in your store's theme. 

<div class="alert alert-info">
Find more details on each block accessing the <a href="https://vtex.io/docs/apps/all/">VTEX IO app documentations</a>.
</div>

### Product Summary Image block

When we talk about product images being rendered in the Product Summary component, a best practice is to use the `aspectRatio`, `width`, `height` and `maxHeight` props pertaining to the `product-summary-image` block.

These props will let **Product Summary images be of identical size** when rendered, even if each image was originally submitted with a different size in the admin's Catalog.

This in turn allows your store's Shelf, for example, to have image consistency across all products being displayed, differently from the Shelf example below: 

![beat-practices-images](https://user-images.githubusercontent.com/52087100/80645249-3bdbf680-8a41-11ea-8f63-8b96b20f7c4b.png)

To implement these props in your theme, access the [**Product Summary Image**](https://vtex.io/docs/components/all/vtex.product-summary@2.53.3/product-summary-image/) block documentation.