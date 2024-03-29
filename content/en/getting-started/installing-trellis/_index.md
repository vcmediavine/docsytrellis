---
title: "Installing Trellis"
type: docs
weight: 10
description: >
  Follow these steps to ensure a successful Trellis installation.
---
{{< card header="**Before You Begin**"  >}}

- **Determine your development environment:** You can choose to develop your child theme on your local computer or in a hosted environment that’s running WordPress. When developing on a local computer, Critical CSS and REST API warnings might appear, depending on your configuration. Trellis needs to communicate with Mediavine's Trellis Services API (included in your subscription) to generate Critical CSS files.

- **Check your WordPress and PHP versions:** To install Trellis, you must be using WordPress 5.2 or higher and have at least PHP 7.3 installed.
- **(Optional for development) Install an SSL certificate:** An SSL certificate lets Trellis create optimized CSS files for faster performance (your Trellis instance also needs the ability to communicate with the Mediavine Trellis Services API). If you don’t have an SSL certificate installed, you’ll see a Critical CSS error in the WP Dashboard and in Trellis Settings. However, this is optional. You can ignore this warning while developing your child theme in a non-production environment.
- **Purchase a License:** Go to the [Mediavine Marketplace](https://marketplace.mediavine.com/trellis/) to purchase a Trellis license and download the installation files. A valid license unlocks all Trellis features.

{{< /card >}}

## Install the Trellis Theme Framework

1. In the WordPress Admin Dashboard, go to **Appearance > Themes**.
2. Click **Add New**.
3. Click **Upload Theme**.
4. Click **Choose File** and select the Mediavine-Trellis ZIP file you received with your subscription purchase.
5. Click **Install Now**.
6. Click **Activate**.

Trellis is now running on your WordPress site. The Trellis Core minimally-styled templates will be used to display content.

## Activate Your Trellis License

1. In the WordPress Admin Dashboard, go to **Appearance > Mediavine Trellis**.
2. Click **License**.
<br />
<img src="trellis-0.18.0-settings-license.png" alt="Trellis Settings panel." width="200px" />
3. Enter your Trellis license in the **License Code** box.
4. Click **Activate License**.

You now have access to all of the Trellis Theme Framework features.

{{% alert title="Note" %}} If you’ve installed Trellis on an existing site with posts and images, it’s a good idea to set your Featured Image Size to match your new theme. Click **Display** and go to the **Featured Image Size** option and select the ratio you’d like to use. Then click the **Regenerate Featured Images** button. This will instruct WordPress to recreate your featured images on posts using the ratio you selected. See [How to Regenerate Your Image Sizes](https://product-help.mediavine.com/en/articles/5528297-how-to-regenerate-your-image-sizes-in-trellis) in the Trellis Help Center for more information.{{% /alert %}}

## (Optional) Install the Trellis Images Plugin

Trellis Images is a helper plugin that automatically creates a WebP version of legacy image formats and stores it in your site’s uploads folder (the original image is never altered or removed). WebP images load faster and score higher in Google’s Core Web Vitals.

1. In the WordPress Admin Dashboard, go to **Plugins > Add New**.
2. Click **Upload Plugin**.
3. Click **Choose File** and select the Trellis Images plugin you received with your subscription purchase.
4. Click **Install Now**.
5. Click **Activate Plugin**.

## (Optional) Install the Trellis Child Themes

Trellis comes with three child themes: Bamboo, Birch, and Wisteria, each available as a separate installation file with your subscription purchase. When developing a new child theme, it can be useful to refer to these Mediavine-built themes to see how different Trellis features are implemented.

{{% alert title="Note" %}} You don’t need to install or activate a child theme to see Trellis at work. Trellis Core comes with minimally-styled templates that will show you all the options that are available. Some of the included child themes will not show all of the options in Trellis Settings or may include functionality specifically coded for that theme. {{% /alert %}}

1. Click **Add New**.
2. Click **Upload Theme**.
3. Click **Choose File** and select a Trellis child theme ZIP file included with your subscription purchase.
4. Click **Install Now**.
5. Click **Activate**.

## What’s Next?

- Learn about Trellis’ [Changes to WordPress]({{< ref "changes-to-wordpress" >}})
- Get to know the available options in [Trellis Settings]({{< ref "trellis-settings" >}})
- Get started [creating a Trellis child theme]({{< ref "creating-your-child-theme" >}})