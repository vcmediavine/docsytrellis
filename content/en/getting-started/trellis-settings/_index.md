---
tags: ["settings","critical css"]
title: "Trellis Settings"
type: docs
weight: 30
description: >
  When you activate Trellis, a new menu becomes available under Appearance in the WordPress Admin Dashboard. 
---
Trellis Settings provides options that a publisher can change to alter a theme’s behavior or to perform maintenance functions. Not all settings may be available in a child theme. Some require the theme developer to specifically add support.

Also, if you choose to create new or additional templates (or create an entirely new CSS stylesheet), it’s up to you to connect the Trellis Settings options to elements in your theme.

## Using Settings in a Child Theme

The Usage column in the table below describes how a setting is incorporated into a child theme. Some settings are enabled via WordPress’ theme support function; some are accessed via CSS variables; others require adding code to child theme templates; and some require a combination of these methods.

While it’s possible to read the settings programmatically (and then perform an action on them), this page focuses on explaining how the settings are incorporated in the Trellis Core templates.

### Theme Support

To enable a feature via WordPress’ theme support function, include the following code in the child theme’s functions.php file at the end of the `mv_trellis_child_set_options()` function:

```php
add_theme_support('{parameter}');
```

{{% alert title="Note" %}}
If multiple settings use the same theme support parameter, they will all become visible in Trellis Settings when enabled.
{{% /alert %}}

For example, if adding support for the Background Accent Color setting, the code would look similar to:

```php
function mv_trellis_child_set_options() {
    $child_version = '{your-child-version}';

    \Mediavine\Trellis\Options::set_multiple(
        [
            'child_name'    => '{trellis-child-theme-name}',
            'child_version' => $child_version,
            'child_css'     => get_stylesheet_directory_uri() . "/assets/index.$child_version.css",
            'child_js'      => get_stylesheet_directory_uri() . "/assets/index.$child_version.js",
        ]
    );
/** add theme support for background accent color */
  add_theme_support('mv_trellis_background_accent_color');
}
```

Multiple `add_theme_support()` methods can be added to the function, if needed.

### Using Trellis CSS Variables

Trellis’ default CSS stylesheet incorporates all the settings shown in the table. If you want to make use of a setting color or font in a different part of your theme, you’ll need to reference a Trellis CSS variable.

{{% alert color="warning" title="Important" %}}
Do not redeclare any Trellis CSS variables. Doing so will break Trellis functionality.
{{% /alert %}}

The syntax to use a CSS variable is:

```text
var({--trellis-variable-name}, {optional-fallback-value})
```

For example, if using the Trellis Primary Color as the background for a div element (with a fallback value of white), you would use:

```text
div { background-color: var(--mv-trellis-color-primary, #ffffff); }
```

### Adding Code to Templates

Some settings will reference functions or code that needs to be included in a template file. Refer to the function, hook, filter, or named Trellis Core templates to see how they’re used.

## Display Settings

### Font Sizes and Typefaces

| Setting | Description | Usage |
| --- | --- | --- |
| Change Font Size | Sets the font size for the body element. | CSS variable: <br /> `--mv-trellis-font-size` |
| H1 Font Size | Sets the default size for H1 headings. | Add theme support and use a CSS variable.<br /><br />Theme support parameter: `mv_trellis_headings_control` <br /><br />CSS variable:<br />`--mv-trellis-h1-font-size` |
| Apply H1 Size to All Headings | Adjusts the sizes of H2 through H6 elements based on the H1 size. If enabled, the following conversions are used: <br /><br />h2 = h1 * 0.75rem <br /> h3 = h1 * 0.67rem <br /> h4 = h1 * 0.63rem <br /> h5 = h1 * 0.56rem <br /> h6 = h1 * 0.5rem | Theme support parameter: <br /> `mv_trellis_headings_control` <br /> <br />CSS variable:<br /> `--mv-trellis-h2-font-size` <br /> `--mv-trellis-h3-font-size` <br /> `--mv-trellis-h4-font-size` <br /> `--mv-trellis-h5-font-size` <br /> `--mv-trellis-h6-font-size` |
| Body Font | Sets the font of the body element. Select a Web Safe font for best performance. | CSS variable: <br /> `—-mv-trellis-font-body` |
| Heading Font | Sets the font for all headings. Select a Web Safe font for best performance. | CSS variable: <br /> `—-mv-trellis-font-heading` |

### Colors

| Setting | Description | Usage |
| --- | --- | --- |
| Primary Color | Sets a main color for use in child themes. Trellis defaults to using this color for links, buttons, and other elements in the Trellis Core theme and in Birch, Wisteria, and Bamboo. | CSS variable:<br />`--mv-trellis-color-primary` |
| Secondary Color | Sets an alternate color for use in child themes. Trellis defaults to using this color for hover effects, alternate buttons, and other secondary elements in the Trellis Core theme and in Birch, Wisteria, and Bamboo. | CSS variable: <br /> `--mv-trellis-color-secondary` |
| Background Accent Color | Sets the background color of some elements like page and post headers in the Trellis Core theme and in Birch and Wisteria. <br /><br />This setting is not used in the Bamboo child theme. | Add theme support and use a CSS variable. <br /><br />Theme support parameter: <br  />`mv_trellis_background_accent_color` <br /><br />CSS variable: <br />`--mv-trellis-color-background-accent` |
| H1 Color | Sets the color of all H1 headings in the Trellis Core theme and in Birch, Wisteria, and Bamboo. | Add theme support and use a CSS variable. <br /><br /> Theme support parameter:  <br /> `mv_trellis_headings_control` <br /><br /> CSS variable: <br /> `--mv-trellis-h1-font-color` |
| Apply H1 Color to All Headings | Sets the color of all H2 to H6 elements to match the H1 color setting in the Trellis Core theme and in Birch, Wisteria, and Bamboo. | Add theme support and use a CSS variable. <br /><br /> Theme support parameter: <br /> `mv_trellis_headings_control` <br /><br />CSS variable: <br /> `--mv-trellis-heading-font-color` |

### Post Meta

| Setting | Description | Usage |
| --- | --- | --- |
| Post Meta Display - Top | Select which post meta to display in the post header. Options include: Comment Count, Author, Date, and Categories. <br /><br />If Yoast SEO is installed, you can show Yoast breadcrumbs. | Refer to the article-meta-header template part in Trellis Core to see how this is implemented. |
| Post Meta Display - Bottom | Select which post meta to display in the post footer. Options include: Author, Date, and Categories. <br /><br />If Yoast SEO is installed, you can show Yoast breadcrumbs. | Refer to the article-meta-footer template part in Trellis Core to see how this is implemented. |
| Post Meta Date Display | Specifies the date to display in the post header. Options include: Display Modified, Display Published, or Display Both. | Output by the `mv_trellis_entry_date()` function. Refer to the article-meta-header or article-meta-footer template parts in Trellis Core for reference. |

### Images

| Setting | Description | Usage |
| --- | --- | --- |
| Site Logo | Sets an image for use as a logo in the site header. If there is no site logo, the site title will be shown. <br /><br /> In the Trellis Core theme and Bamboo and Birch, the logo will display inline with the main navigation. <br /><br />In Wisteria, the logo will display next to the sticky post on the homepage, and inline with the main navigation on posts and pages. | Output by the `mv_trellis_site_title()` function. See [Functions]({{< ref "functions" >}}) for more information. |
| Change logo height | Sets the max logo height value that can be shown in the header.<br /><br />Full options include:<br/>\- Small (50 px)<br/>\- Medium (75 px)<br/>\- Large (100 px)<br/>\- Extra Large (150 px) | CSS variable: <br /> `--mv-trellis-max-logo-size` |
| Display Featured Images | Shows featured images on posts before the post content. | See content-article template part in Trellis Core for reference. |
| Hide Featured Image from Small Screens | Hides the post featured image when the visitor is using a device with a viewport width smaller than 600 px. <br /><br /> Displaying featured images to mobile devices impacts the Largest Contentful Paint (LCP) score, one of Google's Core Web Vitals. | Adds a `hide-featured-image-on-mobile` class to the `<body>` tag when post featured images are enabled but hidden on mobile. |
| Featured Image Size | Sets the thumbnail size used for post thumbnails. <br /><br /> Also controls the additional image sizes Trellis instructs WordPress Core to create. See [Image Delivery and Optimizations]({{< ref "image-delivery" >}}) in Advanced Topics for more information. | Controlled by Trellis Settings.  |

### Footer

| Setting | Description | Usage |
| --- | --- | --- |
| Hide Mediavine/Trellis footer links | Removes the Mediavine/Trellis footer links. | Output by the `tha_footer_bottom` hook. <br /><br />See [Hooks]({{< ref "hooks" >}}) for more information. |
| Footer Copyright Text | Adds personalized copyright text to the footer. Supports HTML markup, including links. | Output by the `tha_footer_bottom` hook. <br /><br />See [Hooks]({{< ref "hooks" >}}) for more information. |

### Layout

| Setting | Description | Usage |
| --- | --- | --- |
| Enable Search Bar | Adds a search bar to the site header. | See header template part in Trellis Core for reference. |
| Layout space | Adjusts the margins between key layout elements like the primary content, sidebar, and widgets. The following defaults are used for new themes (Birch, Wisteria, and Bamboo use their own settings): <br /><br /> Compact = 10 px <br /> Comfortable = 20 px | CSS Variable: `--mv-trellis-gutter` |
| Display Tag Links | (As of Trellis 0.17.0) Controls if tag links are output in the article footer when viewing a post. | Controlled by Trellis Settings. |
| Article Navigation | (As of Trellis 0.17.0) Controls whether a link to the next or previous post is added to the bottom of a post. | Controlled by Trellis Settings. |
| Enable Trellis comments | Sets Trellis as the commenting engine for the site. <br /><br /> See [Trellis Comments]({{< ref "trellis-comments" >}}) in Advanced Topics for more information. <br /> <br /> **Warning**: If you are using an additional third party comment tool, deactivating Trellis Comments may be necessary for compatibility. | See the comments template in Trellis Core for reference. |

## Advanced Settings

### Google Analytics

| Setting | Description | Usage |
| --- | --- | --- |
| Universal Analytics Tracking ID | The legacy Google Analytics UA Tracking ID. | Controlled by Trellis Settings. Inserted within the `<head>` element. |
| Google Analytics 4 Tracking ID | The newer Google Analytics 4 (GA4) Tracking ID. | Controlled by Trellis Settings. Inserted within the `<head>` element. |
| Delay Google Analytics Load | Forces a three second delay to the initial Google Analytics load. While visitors who leave your site within that time will not be tracked, site performance will improve. | Controlled by Trellis Settings. |

### SEO

| Setting | Description | Usage |
| --- | --- | --- |
| Trellis SEO Output | Enables meta descriptions, schema output (via JSON-LD), and Open Graph tags for your site. <br /><br /> Note: This option is automatically disabled if Trellis detects Yoast, RankMath, or AIO as installed and active. It cannot be turned on while these plugins are active. <br /><br /> For all other SEO plugins, disable this to prevent duplicate SEO data. | Controlled by Trellis Settings. |

### Optimization

| Setting | Description | Usage |
| --- | --- | --- |
| JavaScript Optimization | Enables minification of JavaScript files and defers loading for better performance.  <br /><br /> Note: If Trellis detects another plugin is performing JavaScript optimizations, it will automatically disable its own optimization functions. <br /><br /> Recognized plugins include Autoptimize, Clearfy Cache, Jetpack, Litespeed Cache, NitroPack, SG Optimizer, W3 Total Cache, WP Fastest Cache, and WP Rocket. | Controlled by Trellis Settings. |
| JavaScript Exclusions | Matching full or partial URLs in this list are excluded from any deferment or minification performed by Trellis. <br /><br /> Note: This setting is only visible when JavaScript Optimization is enabled. | Controlled by Trellis Settings. |

### Permanent Actions

| Setting | Description | Usage |
| --- | --- | --- |
| Reset Settings | Sets the theme back to default settings (except for the license field). <br /><br /> **Warning:** This cannot be undone. | Controlled by Trellis Settings. |
| Trellis Cache | Clears the Trellis cache. Use if new Trellis features or settings are not appearing. <br /><br /> **Warning:** This cannot be undone. | Controlled by Trellis Settings. |
| Regenerate Images | Regenerates all image sizes on your site. <br /><br /> This is used if images other than your featured images are displaying at the wrong size. See [How to Regenerate Your Image Sizes](https://product-help.mediavine.com/en/articles/5528297-how-to-regenerate-your-image-sizes-in-trellis) in the Trellis Help Center for more information. | Controlled by Trellis Settings. |
| Rebuild Active Compatibility Plugins List | Regenerates a list of active plugins that require compatibility code to work properly with Trellis. See [Trellis Themes: Conflicts and Compatibilities](https://product-help.mediavine.com/en/articles/5046317-trellis-themes-conflicts-and-compatibilities) in the Trellis Help Center for more information. | Controlled by Trellis Settings. |

## PWA Settings

| Setting | Description | Usage |
| --- | --- | --- |
| Enable PWA | Enables PWA support for your site. If enabled, it allows users to view your blog as a progressive web app on their desktop or mobile device. | Controlled by Trellis Settings. |
| PWA Short Name | Sets the display name of the app on the installed device. <br /><br /> **Warning:** A Short Name is required for PWA to operate. | Controlled by Trellis Settings. |
| Theme Color | Sets the color of the URL bar on supported devices to match your site style. | Controlled by Trellis Settings. |
| PWA Site Icon | Sets the image for use as the PWA icon. <br /><br /> **Warning:** A Site Icon is required for PWA to operate. | Controlled by Trellis Settings. |

## License Settings

| Setting | Description | Usage |
| --- | --- | --- |
| Trellis License | Unlocks Trellis’ full features. Visit the [Mediavine Marketplace](https://marketplace.mediavine.com/) to purchase a license. | Controlled by Trellis Settings. |

## Hooks Settings

| Setting | Description | Usage |
| --- | --- | --- |
| Add custom HTML code to the `<head>` tag | Useful for Google Site verification HTML meta tags or a Pinterest domain verification HTML tag. See [Trellis Hooks Settings Overview](https://product-help.mediavine.com/en/articles/5592808-trellis-hooks-settings-overview) in the Trellis Help Center for more information. | Controlled by Trellis Settings. Added via the`tha_head_bottom` hook. See [Hooks]({{< ref "hooks" >}}) for more information. |
| Add custom content after the page header and menu | (As of Trellis 0.17.0) This hook is useful to add anything on pages just after the header and before the content. See [Trellis Hooks Settings Overview](https://product-help.mediavine.com/en/articles/5592808-trellis-hooks-settings-overview) in the Trellis Help Center for more information. | Controlled by Trellis Settings. Added via the `tha_content_before` hook. See [Hooks]({{< ref "hooks" >}}) for more information. |
| Add custom content between the post heading and the post content | Useful to add anything just before post content. Typically used for affiliate disclaimers and CTAs. See [Trellis Hooks Settings Overview](https://product-help.mediavine.com/en/articles/5592808-trellis-hooks-settings-overview) in the Trellis Help Center for more information. | Controlled by Trellis Settings. Added via the `tha_aside_before_entry_content` hook. See [Hooks]({{< ref "hooks" >}}) for more information. |
| Add custom content after the post content | Useful to display anything just after the post content. Typically used for CTAs. See [Trellis Hooks Settings Overview](https://product-help.mediavine.com/en/articles/5592808-trellis-hooks-settings-overview) in the Trellis Help Center for more information. | Controlled by Trellis Settings. Added via the  `tha_content_after` hook. See [Hooks]({{< ref "hooks" >}}) for more information. |
| Add custom HTML code to the end of the `<body>` tag | Useful to add additional scripts required by external services such as newsletters or email opt-in forms. Anything added here should not be needed at the time of the First Contentful Paint (FCP). See [Trellis Hooks Settings Overview](https://product-help.mediavine.com/en/articles/5592808-trellis-hooks-settings-overview) in the Trellis Help Center for more information. | Controlled by Trellis Settings. Added via the `tha_body_bottom` hook. See [Hooks]({{< ref "hooks" >}}) for more information. |

## Critical CSS Settings

### Settings

| Setting | Description | Usage |
| --- | --- | --- |
| Enable Critical CSS | Improves your site's performance by using Critical CSS and Non-Critical CSS files. See [Critical CSS]({{< ref "/advanced-topics/critical-css" >}}) in Advanced Topics for more information. | Controlled by Trellis Settings.  |
| Purge All Critical CSS | Removes all Critical CSS files for the site. New Critical CSS files are added as non-logged in users visit the site. The site's original CSS code will be served until Critical CSS is regenerated. | Controlled by Trellis Settings. |

### Exclusions
| Setting | Description | Usage |
| --- | --- | --- |
| Post/Page Exclusions | (As of Trellis 0.17.0) Shows all posts and pages where Critical CSS has been disabled manually in the WordPress Editor. | Controlled by Trellis Settings. |
| Force Non-Critical CSS | Adds selectors to the secondary Non-Critical CSS file.  <br /><br /> Trellis creates the Non-Critical CSS file automatically. This setting is intended for compatiblity purposes. It lets publishers manually force selectors into the Non-Critical CSS file. These are typically selectors that need to be added via JavaScript after the page loads. See [Critical CSS]({{< ref "/advanced-topics/critical-css" >}}) in Advanced Topics for more information. | Selectors can be added programmatically via  `mv_trellis_css_allowlist`. See [Filters]({{< ref "/reference/filters" >}}) for more information. |
| Force Critical CSS | Adds selectors to the primary Critical CSS file.<br /><br />Trellis creates a Critical CSS file automatically. Styles that match Critical CSS selectors are added as inline styles to the page markup that appears in the initial viewport. <br /><br /> This setting is intended for compatibility purposes. It lets publishers manually add selectors that are not part of the initial viewport of a page. Some of these styles may be necessary to prevent layout shift or a flash of unstyled content on page load. See [Critical CSS]({{< ref "/advanced-topics/critical-css" >}}) in Advanced Topics for more information. | Selectors can be added programmatically via `mv_trellis_css_force_keep`. See [Filters]({{< ref "/reference/filters" >}}) for more information. |

## What’s Next?

- Get started [creating a Trellis child theme]({{< ref "creating-your-child-theme" >}})
- Read more about [Trellis Hooks]({{< ref "Hooks" >}})
- Read more about [Trellis Filters]({{< ref "/reference/filters" >}})