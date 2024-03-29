---
tags: ["critical css"]
title: "Critical CSS"
type: docs
weight: 10
description: >
  Critical CSS is one of Trellis’ most important features and has a big impact on Google’s Core Web Vitals. 
---
Critical CSS reduces load time by generating two optimized CSS files: one for inline styling of content that appears in the initial viewport for a page, and another linked file for styling the rest of the page. Trellis creates these files for each page of your WordPress site.

{{% alert title="Note" %}}
In this article, a page refers to either a post or an actual page in WordPress. It’s whatever gets served to your reader when they visit your site in a browser.
{{% /alert %}}

## How Is Critical CSS Generated?

1. When a page is first visited by a non-logged in user, your Trellis instance submits it to the Trellis Services API hosted by Mediavine. Access to this service is included in your license.
2. The page is rendered in a browser with a 1300 x 900 px viewport and its CSS stylesheet is audited.
3. Any CSS styles that affect content in this viewport are saved into a minified primary Critical CSS file.
4. Any CSS styles that fall outside of this viewport are saved into a minified secondary Non-Critical CSS file. CSS styles that are not referenced by elements on the page are completely left out.
5. When the Critical and Non-Critical files are complete, the Trellis Services API notifies your Trellis instance to download them. These files are saved into your WordPress installation (specifically the /wp-content/mvt-critical/ directory).
6. The next time the page is visited by a non-logged in user, the Critical and Non-Critical CSS files are served.

{{% alert title="Note" %}}
The primary Critical CSS file is loaded as inline styles when the page loads. The secondary Non-Critical CSS file is loaded as an external stylesheet. This renders initial page views much more quickly, as the site includes the most important CSS (the primary Critical CSS styles) in the page markup.
{{% /alert %}}

## How To Determine the Critical CSS Status of a Page

When logged in to WordPress, a Critical CSS Status will appear in the admin bar when you view a page on your site (See [Changes to WordPress]({{< ref "/getting-started/changes-to-wordpress" >}}) for more information). The status tells you where Trellis is in the Critical CSS generation process:

| Status | Description |
| --- | --- |
| Critical CSS - License Required | The site is missing an active Trellis license. Go to **Appearance > Mediavine Trellis** and click **License** to purchase or add a Trellis license. |
| Disabled | Critical CSS generation has been disabled for the post or page in the WP Editor. This status will also be displayed if Critical CSS is disabled on your site (check **Appearance > Mediavine Trellis** and click **Critical CSS**). |
| Error | The page encountered an error while generating the Critical CSS files. See [Troubleshooting]({{< ref "/getting-started/troubleshooting" >}}) for some steps you can take to determine the problem. |
| None | The page has not attempted to generate Critical CSS yet. This can occur if your readers (i.e. non-logged in users) haven't visited it yet. As of Trellis 0.16.0, a page in the Pending or Processing status will switch to None if it doesn’t receive a response from the Trellis Services API after two hours. |
| Pending | (Deprecated in 0.17.0.) The page has been queued for generation of Critical CSS. |
| Processing | The page is currently in the process of generating Critical CSS files. A request has been sent to the Trellis Services API, but the files haven’t been saved to the site yet. |
| Success | The page successfully generated Critical CSS files. |

{{% alert color="warning" title="Important" %}}
When you visit a page while logged in, Trellis **does not** submit it for Critical CSS generation. Automatic generation only happens when a non-logged in user visits the page.
{{% /alert %}}

## When Does Critical CSS Get Refreshed?

Knowing that Critical CSS files are only generated when a non-logged in user views a page, it’s natural to wonder when Trellis will trigger an update to those files. Here are the events that prompt Critical CSS to purge its existing files:

| Event | Description |
| --- | --- |
| Automatic Updates | Whenever Wordpress is automatically updated. |
| Custom functions | The functions `mv_trellis_purge_all_critical_css()` and `mv_trellis_purge_page_critical_css()` will trigger an update. See [Functions]({{< ref "functions" >}}) in the Reference section for more information. |
| Plugin changes | Activating or deactivating a plugin. |
| Critical CSS commands | When logged in, the Manage Trellis JS/CSS menu on the admin bar gives you options to purge Critical CSS for the current page or all pages on the site. |
| Sidebar widget changes | If you add, remove, change position, or change settings on a sidebar widget. |
| Switching themes | Whenever you activate Trellis or a Trellis child theme. |

If you’ve made a significant change to your theme’s design or functionality, you may want to tell Trellis to discard all existing Critical CSS files and rebuild them from scratch (also referred to as purging). For more information on when to use the Purge features, see [Critical CSS in the Admin Bar](https://product-help.mediavine.com/en/articles/4964387-critical-css-in-the-admin-bar) in the Help Center.

## Advanced Functionality

There are instances where you might want to alter Critical CSS functionality because you intend to use your child theme with other plugins. You might also use JavaScript to alter the styling of page elements after page load. In these scenarios, Critical CSS’ default functionality might give you unexpected results. For dynamically altered elements that appear in the initial viewport, you’ll want to consider adding their selectors to the Critical CSS file. If those elements appear outside of the initial viewport, add their selectors to the Non-Critical CSS file.

### Adding CSS to the Critical CSS File

By default, if a CSS selector doesn’t match an element in the initial 1300 x 900 px viewport of a page, it gets saved to that page’s Non-Critical CSS file. This might not be the desired behavior. It's possible that you need some styles to be present at page load to prevent a layout shift or stop a flash of unstyled content for elements close to the viewport, but not in it.

While publishers can add CSS selectors manually to the Force Critical CSS list in Trellis Settings, you can include them programmatically by adding code to your child theme’s functions.php file.

In the example below, selectors are added to an array. You can add full selector names or partial names if you want to match a range of selectors. An `add_filter` is then used to add the matching selectors to Trellis’ Force Critical CSS list. When a page gets submitted to the Trellis Services API, any matching CSS selectors are added to the Critical CSS file.

{{% alert color="warning" title="Important" %}}
If you add selectors to the Force Critical CSS list, be sure to check your pages in a Google Page Speed Insights report during testing. Adding selectors to the Force Critical CSS list may cause an "Unused CSS" warning to appear if the selectors are not specific enough or only appear outside of the initial viewport.
{{% /alert %}}

**Example**

In the example below, a site uses WP Recipe Maker and wants all styles included in the primary Critical CSS file. Since all WP Recipe Maker styles begin with the suffix “wprm,” Trellis will add all of the matching styles.

```php
function theme_forced_styles( $selectors ) {
    $selectors[] = 'wprm';
    return $selectors;
}

add_filter( 'mv_trellis_css_force_keep', 'theme_forced_styles' );
```

You can add multiple styles to the array by using an `array_merge()`:

```php
array_merge( $selectors, [ 'wprm', 'blue' ] )
```

You can also add them individually by using multiple lines:

```php
$selectors[] = 'wprm';
$selectors[] = 'blue';
```

{{% alert title="Note" %}}
Styles added programmatically do not appear in Trellis Settings.
{{% /alert %}}

### Adding CSS to the Non-Critical CSS File

When creating the secondary Non-Critical CSS file, Trellis leaves out any CSS styles that don't apply to elements on the page. This can create issues if elements are added to the page markup after the initial page load. The Trellis Services API does not execute JavaScript at runtime, so styles for these added elements would not be included in the Non-Critical CSS file.

Publishers can add these style selectors manually in Trellis Settings, but if you design your child theme to work with a third-party plugin (or are adding your own JavaScript that impacts content styling) you may want to include selectors programmatically. You do this by adding code to your child theme’s functions.php file.

Just like with Force Critical CSS, the example below shows a custom function where selectors are added to an array. You can add full selector names or partial names if you want to match a range of selectors. An `add_filter` is then used to add the matching selectors to Trellis’ Force Non-Critical CSS list. Any CSS styles that match the expression will get added to the Non-Critical CSS file. 

**Example**

In the example below, dynamic page elements marked with “pop-up” are styled via JavaScript after page load. Specifying “pop-up” will add all matching styles.

```php
function theme_allowlist_styles( $selectors ) {
    $selectors[] = 'pop-up';
    return $selectors;
}

add_filter( 'mv_trellis_css_allowlist', 'theme_allowlist_styles' );
```

You can add multiple styles to the array by using an `array_merge()`:

```php
array_merge( $selectors, [ 'pop-up', 'red' ] )
```

You can also add them individually by using multiple lines:

```php
$selectors[] = 'pop-up';
$selectors[] = 'red';
```

{{% alert title="Note" %}}
Styles added programmatically do not appear in Trellis Settings.
{{% /alert %}}

## Issues with Critical CSS

If you encounter problems using Critical CSS during development, refer to [Troubleshooting]({{< ref "/getting-started/troubleshooting" >}}).