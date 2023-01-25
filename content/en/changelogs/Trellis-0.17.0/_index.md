---
title: "Trellis 0.17.0"
type: no_toc
---

## Changelog

0.17.0

- NEW: Trellis 0.17.0 now requires PHP version 7.3 or higher.
- NEW: Critical CSS settings and features are now available in a separate Critical CSS tab in the Mediavine Trellis Dashboard. Publishers can enable/disable Critical CSS, purge Critical CSS files, add or remove selectors from the Critical and Non-Critical CSS files, and see any Critical CSS issues that have been identified by Trellis. 
- NEW: The Critical CSS tab now features a Post/Page Exclusion table showing any posts or pages where Critical CSS has been disabled. Publishers can re-enable Critical CSS for individual posts or pages using an Enable button.
- NEW: A Purge All Critical CSS button is now available in the Critical CSS tab. This button removes all existing Critical CSS files. New Critical CSS files will be generated as readers visit the site’s pages.
- NEW: A status indicator is now shown on the Trellis icon (Block editor only) and more descriptive text in the Trellis Settings sidebar in the WordPress Editor. This informs publishers if there are any detected Critical CSS issues.
    - Green indicator: This means that Critical CSS files are processing or were successfully generated.
    - Grey indicator: This means that Critical CSS files are pending, disabled, or don’t exist.
    - Red indicator: This means that there was an error generating the Critical CSS files.
- NEW: A Purge Critical CSS button is now available in the WordPress Editor. This lets publishers delete the Critical CSS associated with a single page or post. It will be regenerated when a reader visits the page.
- NEW: A Display Tag Links toggle in Trellis Settings > Display > Layout now controls whether tag links are shown after a post. The default is to show tag links.
- NEW: Publishers can now control whether to show a Next/Previous link on posts via an Article Navigation setting in Trellis Settings. The default is to show the Next/Previous link.
- NEW: Removed Trellis Settings from the WordPress Customizer. Settings are more easily displayed (along with additional configuration options) in the Mediavine Trellis Dashboard.
- NEW: Publishers can now use a Hide Page Title control on any page in the Page editor.
- NEW: For child theme developers, two new functions were added to the Trellis Core front page template (header-content-front-page.php) for static front pages:
    - `mvt_title_before()` fires off the `tha_title_before` hook before the page title output (as long as the title isn’t hidden).
    - `mvt_title_after()` fires off the `tha_title_after` hook after the page title output (as long as the title isn’t hidden).
- CHANGED: Removed the Enable Stale CSS While Revalidating feature. Trellis will now serve the original page/post CSS while the Critical CSS files are regenerating. This may result in a slower site speed until the files are regenerated, but will help reduce confusion for publishers. For example, if a plugin updated a site’s CSS while the stale Critical CSS was shown during regeneration, publishers would think the plugin wasn’t working.
- CHANGED: Renamed the CSS Allowlist section in Trellis Settings to Force Non-Critical CSS.
- CHANGED: Added more detailed descriptions to Force Critical CSS and Force Non-Critical CSS features to help publishers better understand the features.
- CHANGED: Modified how entered CSS selectors are displayed in the Force Critical CSS and Force Non-Critical CSS settings. Values entered for these features are now shown as user interface “chips” which can be removed from the setting by clicking the X control.
- CHANGED: Added descriptive text to the PWA Short Name and PWA Site Icon settings to inform the publisher that these items must be set for the Progressive Web App feature to work.
- CHANGED: Added a caret (>) control to Trellis notices when additional information is available. Previously, notices showed a link which could be missed at a casual glance.
- CHANGED: Added code to resolve a “Links do not have discernible name” failure in the GPSI/Lighthouse accessibility audit. The `aria-hidden="true" tabindex="-1”` attributes are now added to Featured Image tags in the post pagination section.
- CHANGED: Modified the behavior of links in Trellis Settings to open in a new browser tab instead of the current tab. This affects License, Marketplace, and links to help articles.
- CHANGED: Modified admin notices so that they can be dismissed like other notices.
- CHANGED: Removed the Critical CSS Error notice and replaced it with a dismissible Critical CSS Warning notice.
- CHANGED: Added a warning for publishers choosing a 16px font size in Trellis Settings. For optimal ad performance, the font size should be 18px or larger.
- CHANGED: Changed the name of the About Widget to be Trellis About Widget to better identify it as Trellis functionality.
- CHANGED: Child theme developers can no longer use the `mv_trellis_admin_notices`
 filter as it has been removed. This filter removed all notices during an upgrade, but it’s no longer needed due to changes in how Trellis handles notices.
- FIXED: Removed underlines when displaying WP Core button blocks. By default, underlines will only be applied when hovering over these elements.
- FIXED: Added a message and button to the Critical CSS tab when a Trellis license is not found. Publishers will be directed to the Mediavine Marketplace.
- FIXED: Added a compatibility class for RankMath so that publishers can add links to category pages.
- FIXED: Added code to ensure all Trellis theme styling is applied in the Gutenberg and Widget Block editors. Previously, some default WordPress styling could be shown.
- FIXED: Improved the code for the About Widget to better ensure that changes can be saved.
- FIXED: Resolved an issue where a Trellis theme could trigger side-scrolling on smaller screens.
- FIXED: Resolved an issue where the Yoast compatibility class code triggered Trellis to clear its cache, even if Yoast Breadcrumb settings were not changed.
- FIXED: Resolved an issue where Purge Page CSS in the WordPress Admin Bar didn’t work on static home pages.
- FIXED: Added missing RSS feed links on the home page to optimize Trellis sites for Google Discover.
- FIXED: Added `.excerpt-link:hover` styles to the Critical CSS file in Trellis Core. Previously, hover colors could be missing when Critical CSS was generated.
- FIXED: Resolved an issue where the Critical CSS status could show as white when it should be a different color.
- FIXED: Clearing the Trellis cache no longer removes `<link>` tags from Trellis Settings > Hooks.
- FIXED: Added an Error notice in the Widget Editor when the Mediavine Sidebar Ad Hint widget was the last widget in the sidebar. Sidebar Ad Hints should not be the last widget in a sidebar.
- FIXED: Removed the `<title>` tag on the Search Bar SVG image when the Search Bar is enabled. The prevents duplicate title tags in the site HTML.
- FIXED: Resolved an issue with images that had a `width:auto` attribute. In Create and WPRM, this would manifest as images that would appear larger than their actual size.
- FIXED: Resolved an issue where special characters weren’t decoded properly on some mobile browsers.
- FIXED: Resolved an issue where inline images within a paragraph could be downsized to 300px when they should be larger.
- FIXED: Resolved an issue where Trellis Comments were not styled when Trellis and Create were running on a post and the browser was reloaded with the comments on screen.
- FIXED: Resolved a compatibility issue when Jetpack, WooCommerce, and Trellis Comments were active. WooCommerce’s Product Page > Review tab was missing if either Trellis Comments or Jetpack Comments were enabled.
- FIXED: Resolved a Lighthouse fail with the message “Tap targets are not sized properly” message. Pagination link padding was adjusted.
- FIXED: Resolved an issue where Settings > Display > Custom Font Loading could be active even if there was no Trellis license. This only occurred when custom Body and Font settings were selected and the Trellis license was removed.
- FIXED: Removed the link from the Manage Trellis JS/CSS button in the Admin bar so that it isn’t clickable. Previously, clicking on it could show a blank Settings page.