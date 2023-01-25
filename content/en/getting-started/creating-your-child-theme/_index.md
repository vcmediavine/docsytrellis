---
title: "Creating Your Child Theme"
type: docs
weight: 40
description: >
  Trellis Core provides a solid foundation of templates and stylesheets for fast WordPress sites. However, to create a truly unique experience, you’ll want to make a child theme.
---
This document will walk you through the pieces and parts of a Trellis child theme.

{{% alert title="Note" %}}
Trellis child themes follow the same basic structure as any WordPress child theme. You can refer to the [WordPress Theme Handbook](https://developer.wordpress.org/themes/advanced-topics/child-themes/) for detailed information on how child themes operate.
{{% /alert %}}

## Child Theme File Structure

1. Create a new folder for your child theme in your WordPress themes folder.
2. Create the following folder structure inside of your child theme folder:
   
| Folder | Subfolders | Description |
| --- | --- | --- |
| assets | (optional) | A place to store your child theme’s images, CSS, and JavaScript files. |
| template-parts | article<br />content<br />header | A location to store parts of templates that will be used when serving content. Trellis will cache the location of these template parts to serve content faster. |

3. Add a 1200 x 900px screenshot.png file in your child theme folder. This screenshot will be shown on the **Appearance > Themes** page in your WordPress dashboard.

## Add CSS Files

### Create a Style.css File

1. Create a new file called style.css in your child theme folder.
2. Add the following code, replacing the boilerplate text with your own content:

```css
/*
Theme Name: <Your Child Theme Name>
Template: mediavine-trellis
Theme URI: <URL to your child theme's documentation.>
Author: <Your Name or Company Name>
Author URI: <URL to your personal or company website.>
Description: <A short description of your child theme.>
Requires at least: 5.2.0
Version: <Your Child Theme Version (e.g. 0.0.1)>
Text Domain: mediavine
*/
```

The fields are used in the following ways:

### Add Custom CSS Files

You can choose to add your custom CSS to the style.css file or you can create separate CSS files for inclusion in your child theme.

{{% alert title="Note" %}}
We recommend having separate CSS files that are stored in your child theme’s assets folder as a best practice.
{{% /alert %}}

Your custom CSS file can be any name you choose, but we recommend including the child theme version number in the name. This ensures that any CSS changes you make will refresh the browser cache whenever the child theme is upgraded. You’ll define the name and location of your CSS file in your child theme’s functions.php file.

1. Add a custom CSS file to your child theme’s assets folder.

```
wp-content/themes/my-child-theme-name/assets/
```

1. Add your child theme version to the name of your custom CSS file. For example, if your child theme’s version is 0.0.1, name your CSS file index.0.0.1.css.

{{% alert title="Note" %}}
Adding CSS selectors to your child theme’s CSS file will override any matching selectors in Trellis Core’s default CSS stylesheet. If you’d like to start from scratch, you can add code to completely disable Trellis’ default CSS styling. For more information, see CSS Variables in Advanced Topics.
{{% /alert %}}

## Add a Functions.php File

Your child theme’s functions.php file will hold custom functions that change how your theme behaves. It lets you enqueue your CSS stylesheet and customize your theme options.

### Set Basic Definitions

1. Add a functions.php file to your child theme folder.
2. Add the following code to the functions.php, replacing the boilerplate text with your own values:

```php
<?php

/** Basic Definitions **
 * Use mv_trellis_child_set_options() to define the child theme version and other necessary settings. .
 * Options::set_multiple will enqueue stylesheets and scripts.
 * 
 * To learn more about functions available to Trellis child themes, see: https://mediavine.github.io/trellis-docs/docs/functions-php/
 * To learn more about settings available to Trellis child themes, see: https://mediavine.github.io/trellis-docs/docs/settings/
 */

function mv_trellis_child_set_options() {
    $child_version = '<replace with your child theme version number>';

    \Mediavine\Trellis\Options::set_multiple(
        [
            'child_name'    => '<replace with your child theme name>',
            'child_version' => $child_version,
            'child_css'     => get_stylesheet_directory_uri() . "/assets/index.$child_version.css",
        ]
    );

add_action( 'mv_trellis_parent_loaded', 'mv_trellis_child_set_options' );
```

The `$child_version` variable represents the version number of your child theme. We recommend defining it in a variable so that you can reuse it in other places of your child theme code.

The other options you set are described in the table below:

| Field | Description |
| --- | --- |
| Theme Name | The name of your child theme. This is shown on the Appearance > Themes page in your WordPress dashboard and also in Theme Details. |
| Template | The parent theme directory associated with your child theme. To be a Trellis child theme, this must be set to mediavine-trellis. |
| Theme URI | A web address for more information about your theme or for documentation. |
| Author | The name of the author or company that created the child theme. This is shown on the Theme Details page. |
| Author URI | A web address for more information about you or the company that created the child theme. |
| Description | A short description of the child theme. This is shown on the Theme Details page. |
| Requires at least | The minimum WordPress version required to use the child theme. This should be no earlier than 5.2.0, as this is the oldest version of WordPress supported by Trellis. |
| Version | The version number used to identify the iteration of your child theme. |
| Text Domain | Used to support translations. Normally this is set to mediavine. If you use your own text domain, be sure to follow the instructions in WordPress’ Child Theme Internationalization documentation. |

### (Optional) Add Theme Support Options

Add the following code after `Options::set_multiple` to allow the publisher to set accent colors and heading styles using the Mediavine Trellis Dashboard. See Trellis Settings for information on how to connect your code to the settings in your child theme.

```php
/** Accent Color and Headings Support **
 * Use add_theme_support to use accent colors and heading options defined in Trellis Settings.
 */

  add_theme_support( 'mv_trellis_background_accent_color' );
  add_theme_support( 'mv_trellis_headings_control' );
}
```

## Create Template Files

While Trellis supports the WordPress [Template Hierarchy](https://developer.wordpress.org/themes/basics/template-hierarchy/), page load time can be reduced through the use of template parts. Template parts are reusable blocks of code that can be called from different page templates. This allows them to serve up special coding for things like category templates, author templates, and more. Think of template parts as more sophisticated versions of `get_header()` and `get_footer()`.

WordPress has a built-in function for template parts, but Trellis offers a faster function called `mv_trellis_get_template_part()`**.** This custom function caches your template parts and serves them much faster than WordPress’ built-in function. You can see it in use in the Trellis Core and Bamboo, Birch, and Wisteria child themes. See Functions in Reference for more information.

### Built-In Trellis Core Templates

Any template placed in your child-theme’s folder will follow the WordPress Template Hierarchy and override a template in the Trellis parent theme folder. However, we recommend using a similar structure of template parts for your own theme files in order to get the biggest speed boost. 

Trellis Core provides the following templates out of the box:

- comments.php
- footer.php
- header.php
- index.php
- page-full-width.php
- searchform.php
- sidebar.php
- template-parts (directory)
    - article (directory)
        - article-excerpt.php
        - article-meta-footer.php
        - article-meta-head.php
        - article-navigation.php
    - content (directory)
        - content-article.php
        - content-none.php
        - content.php
    - header (directory)
        - header-content-author.php
        - header-content-front-page.php
        - header-content-home.php
        - header-content-singular.php
        - header-content.php
        - header-featured.php
        - header.php
        - navigation.php
        - search-form.php

### Bamboo, Birch, and Wisteria Child Themes

If you’ve installed the Bamboo, Birch, and Wisteria child themes, you’ll find that each one builds upon Trellis Core’s default templates and stylesheets. Some of the child themes have support for accent colors and heading settings, while others don’t. Be sure to activate and look through these child themes for ideas on how to create your own child theme.

### Trellis Template Markup

Trellis also receives higher SEO scores by using [semantic HTML markup](https://www.w3schools.com/html/html5_semantic_elements.asp) in all of its templates. While there’s traditional markup mixed in, large blocks are coded with semantic HTML. Semantic HTML makes it easier for Google’s bots to index your site. It also increases web page accessibility.

Here are some resources to help you understand Trellis’ default markup:

- [Trellis Visual Markup Guide]({{< ref "visual-markup-guide" >}})

## What’s Next?

- Learn how to [test your Trellis child theme]({{< ref "testing-your-child-theme" >}})
- Read more about [Trellis Hooks]({{< ref "hooks" >}})
- Read more about [Trellis Filters]({{< ref "filters-summary" >}})