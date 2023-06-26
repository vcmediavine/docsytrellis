---
title: "Trellis"
type: no_toc
weight: 10
description: >
  A list of changes made to the main Trellis framework, including the Trellis Core templates.
---

## Changelog

### 0.18.1(05/24/2023)

- NEW: Added a new `mv_trellis_skip_eagerload_classes` filter to let developers stop images from being eager loaded.
- FIXED: Addressed an issue where the first image on feed and archive pages was not eager loaded, which could cause LCP to fail.
- FIXED: Stopped eager loading hidden Pinterest images, which prevented the first displayed image from getting eager loaded.
- FIXED: Resolved some Lighthouse errors reported for PWA icons. The “all” attribute for purpose was changed to “any” in the manifest.json file.
- FIXED: Resolved cURL 28 errors on Non-Critical CSS files which would prevent them from downloading. This could occur on servers with a lot of CSS markup where the timeout of cURL requests is too short.

### 0.18.0 (04/03/2023)

- NEW: When adding custom HTML to Hooks in Settings, Trellis will perform a validation after clicking Save. If unsupported or improperly formatted HTML is detected, a popup window will appear alerting the publisher. Buttons allow the publisher to go back to edit the HTML or have Trellis remove it.
- NEW: A “Purchase Trellis” message now appears in the Trellis pane of the WordPress Editor if an active license is missing. A link will take the publisher to the Mediavine Marketplace.
- CHANGED: The Purge Page Critical CSS button will now only appear in the WordPress Editor if the Critical CSS status is Success.
- CHANGED: The Schema Type control in the WordPress Editor will no longer appear if Trellis SEO is disabled. Trellis only outputs schema information when a site is using Trellis SEO.
- CHANGED: Replaced the hand icon used for the Hooks setting with an actual hook icon.
- CHANGED: Added help text to the Trellis pane in the WordPress Editor if Critical CSS is disabled in Trellis Settings. Previously, Critical CSS functions in the editor would just disappear, which could confuse the user.
- CHANGED: Added BlinkMacSystemFont to Trellis’ default font stack. Previously, some Chrome users could see Helvetica appear, which is not a web-safe font.
- CHANGED: Hid the “Hide Featured Image from Small Screens” setting when the “Display Featured Images” setting is disabled.
- CHANGED: Adjusted copy in Advanced Settings > Trellis SEO for Article Schema Type so that publishers will understand that it only applies to new posts when enabled. Publishers can change the Schema Type on existing posts in the WordPress Editor.
- CHANGED: Critical CSS is now cleared when a user adds or updates CSS in the Customizer, and when a license is activated.
- CHANGED: Added a “Critical CSS - License Required” status when a site is missing an active Trellis license. Critical CSS is only served with an active license. The new status is a link that takes the user to the License tab of Trellis Settings.
- CHANGED: Improved copy in the Posts/Page Exclusions table of Trellis Settings. A better explanation is now shown for posts where Critical CSS was disabled in Trellis versions older than 0.17.0.
- CHANGED: Adjusted lazy loading code so that the first image in a post is eager loaded.
- CHANGED: Moved WebP image swapping code from Trellis Core to Trellis Images.
- CHANGED: Improved copy for the Heading Font and Body Font settings in Trellis Settings. A link to a Help Desk article will explain what fonts will be used if a web-safe font is not available.
- FIXED: Improved accessibility on feed pages for keyboard and screenreader users by adjusting HTML on the “Read More” link.
- FIXED: Removed unnecessary spacing that appeared after clicking the button in the Regenerate Images section of Display Settings.
- FIXED: Resolved HTML validation errors with post tag links. Previously, <p> tags could appear within <span> tags, which was incorrect. The <span> was changed to a <div>.
- FIXED: Added code to prevent unbalanced HTML tags that could appear in legacy child themes when using Trellis Comments.
- FIXED: Adjusted a query for Trellis Comments to only get approved comments that populate a hidden div used for SEO purposes.
- FIXED: Improved compatibility when using WP Rocket. Previously, some changes to Trellis Settings would not take effect until WP Rocket’s cache was cleared.
- FIXED: Adjusted code so that the `can_dismiss` property of Admin Notices works properly. Previously, Admin Notices could always be dismissed even when the property was set to false.
- FIXED: Updated how Trellis applies user-specified CSS on images due to recent changes in WordPress Core. User-specified CSS classes entered on images in the WordPress Editor should appear in the immediate parent tag. They were being added to a tag above the parent tag.
- FIXED: Resolved `preg_match` and `strip_tag` deprecation notices when using PHP 8.1.

### 0.17.2 (02/28/2023)

- FIXED: Replaces absolute path stored in compatibility class options with relative path.
- FIXED: Adds check to ensure that file exists before attempting to load compatibility classes.

### 0.17.1 (02/09/2023)

- FIXED: Ensures that Trellis' local model script is not optimized by WP Rocket.

### 0.17.0 (01/30/2023)

- NEW: Trellis 0.17.0 now requires PHP version 7.3 or higher.
- NEW: Critical CSS settings and features are now available in a separate Critical CSS tab in Trellis Settings. Publishers can enable/disable Critical CSS, purge Critical CSS files, add or remove selectors from the Critical and Non-Critical CSS files, and see any Critical CSS issues that have been identified by Trellis. 
- NEW: The Critical CSS tab now features a Post/Page Exclusion table showing any posts or pages where Critical CSS has been disabled. Publishers can re-enable Critical CSS for individual posts or pages using an Enable button.
- NEW: A Purge All Critical CSS button is now available in the Critical CSS tab. This button removes all existing Critical CSS files. New Critical CSS files will be generated as readers visit the site’s pages.
- NEW: A status indicator is now shown on the Trellis icon (Block editor only) and more descriptive text in the Trellis Settings sidebar in the WordPress Editor. This informs publishers if there are any detected Critical CSS issues.
    - Green indicator: This means that Critical CSS files are processing or were successfully generated.
    - Grey indicator: This means that Critical CSS files are pending, disabled, or don’t exist.
    - Red indicator: This means that there was an error generating the Critical CSS files.
- NEW: A Purge Critical CSS button is now available in the WordPress Editor. This lets publishers delete the Critical CSS associated with a single page or post. It will be regenerated when a reader visits the page.
- NEW: A Display Tag Links toggle in Trellis Settings > Display > Layout now controls whether tag links are shown after a post. The default is to show tag links.
- NEW: Publishers can now control whether to show a Next/Previous link on posts via an Article Navigation setting in Trellis Settings. The default is to show the Next/Previous link.
- NEW: Removed Trellis Settings from the WordPress Customizer. Settings are more easily displayed (along with additional configuration options) in Trellis Settings.
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

### 0.16.1 (08/24/2022)

- FEATURE: Adds a new setting to Enable/Disable Trellis JS Optimizations.
- FEATURE: Disables JS Optimizations when Autoptimize JS Optimizations are enabled
- FEATURE: Disables JS Optimizations when NitroPack is enabled
- FEATURE: Disables JS Optimizations when Litespeed Cache JS Optimizations are enabled
- FEATURE: Disables JS Optimizations when WP Fastest Cache JS Optimizations are enabled
- FEATURE: Disables JS Optimizations when W3 Total Cache JS Optimizations are enabled
- FEATURE: Disables JS Optimizations when Clearfy Cache JS Optimizations are enabled
- FEATURE: Disables JS Optimizations when WP Rocket JS Optimizations are enabled
- FEATURE: Disables JS Optimizations when Jetpack JS Optimizations are enabled
- FEATURE: Disables JS Optimizations when SG Optimizer JS Optimizations are enabled
- FIX: Resolves an issue with the Rebuilding Minified JS action not functioning properly
- FIX: Enables partial JS file URLs to be used instead of just full JS file URLs
- FIX: Resolves error when localizing the same font for Body Font and Heading Font settings
- FIX: Removes the code that automatically added images to the image generation queue when pages are viewed
- FIX: Removes Link To Issues Tab From Critical CSS Status Bar
- CHANGE: Removes the need to rebuild minified JS after adding a JS file exclusion
- CHANGE: Adds image selected, for the About Me Widget, to the image generation queue when the correct size doesn’t exist
- CHANGE: Stops the process of getting the count of images in the image generation queue when server resources aren't available
- CHANGE: Removes Critical CSS Error notices
- CHANGE: Sends Critical CSS Errors with REST API check
- CHANGE: Removes Issues Tab
- CHANGE: Reduces Critical CSS timeout duration and time between REST request tests to 48 hours

### 0.16.0 (07/13/2022)

- FEATURE: Added Create compatibility class to add its critical css selectors to the forceInclude filter
- FEATURE: WP Rocket specific code moved to compatibility class
- FEATURE: New way to process settings and database updates when the theme is updated
- FEATURE: Links the post meta Author name to their Website url, or falls back to the Author Posts url
- FEATURE: New setting to disable Trellis comments/Jetpack compatibility class
- FEATURE: Added public functions for purging critical css, mv_trellis_purge_page_critical_css and mv_trellis_purge_all_critical_css
- FEATURE: Admin update notices are dismissible
- FEATURE: Added theme supports check for mvt_hooks to check for Trellis specific hooks
- FEATURE: Added function ’mvt_content_header_after’ to fire new ‘hook tha_content_header_after' immediately after closing </header> content tag
- FEATURE: Added a link to the MV Marketplace when viewing Theme Details
- FEATURE: Adds “disabled” to list of possible Critical CSS statuses displayed on WordPress Admin Bar
- FEATURE: Javascript Optimization exclusion setting
- FEATURE: Posts and Pages with "Processing" Critical CSS Status are set back to "None" after 2 hours
- FEATURE: mvt_processing_css_status_timeout filter added for altering the timeout of "Processing" status Critical CSS
- FEATURE: Added "Show on mobile" setting for all blocks in the Gutenberg widget editor
- FEATURE: Added filter mv_trellis_post_link_featured_image_sizes for post link featured images sizes attribute
- FEATURE: Ability to process all image sizes in queue
- FEATURE: REST endpoint for adding images to queue
- FEATURE: 2nd level mobile menu drop-down
- FEATURE: Display notice when font fails to localize
- FEATURE: Adds admin notice when Trellis issues present with a link to issues page
- FEATURE: Collapsible Notice Messages
- FEATURE: Adds filter mv_trellis_disable_add_async_styles to disable adding async to enqueued styles
- FEATURE: Adds filter mv_trellis_disable_add_async_attribute to disable adding async to enqueued scripts
- FEATURE: Adds filter mv_trellis_disable_convert_iframe_to_lazyload_when_enabled to disable adding or modifying iframe loading attribute
- FEATURE: Adds filter mv_trellis_disable_{$this->slug}_compatibility to disable adding plugin compatibility code
- FEATURE: Adds filter mv_trellis_disable_convert_image_to_lazyload_when_enabled to disable adding or modifying image loading attribute
- FEATURE: Adds filter mv_trellis_disable_set_image_data_pin_attribute to disable adding data-pin-media attribute
- FEATURE: Adds filter mv_trellis_disable_set_image_dimensions to disable setting image dimensions
- FEATURE: Adds filter mv_trellis_disable_set_image_cls_aspect_styles to disable setting and adding aspect ratio styles
- FEATURE: Adds filter mv_trellis_disable_process_images to disable processing all image optimizations
- FEATURE: Adds GA4 Support
- FEATURE: Images that Trellis generates for src-set are now put into a queue only if they don't exist and are needed
- FEATURE: Image generation queue runs as a background process that scales with server resources
- FEATURE: Add images to size generation queue on post save
- FEATURE: Ability to regenerate all images and featured images in Trellis Settings
- FEATURE: Reduced number of custom image sizes created when a one is uploaded
- FEATURE: Expands on functionality of collapsible admin notices with collapsed label and collapsed message text
- FIX: No longer hiding WP Rocket settings
- FIX: Comment forms are removed on posts with comments disabled when using Trellis Comments
- FIX: Removed Trellis font selection settings from the Customizer
- FIX: Adds 'ggnoads' class to post navigation images to prevent gum gum ads on those images
- FIX: Replaced cUrl with wp_remote_get for font localization
- FIX: Reduces Critical CSS selectors by only pulling used WP Blocks on the current page
- FIX: Removes automatic adjustment of WP Rocket's settings when the plugin is activated
- FIX: Post Thumbnail Size now based on selected Featured Image Size in Trellis settings
- FIX: Removes excess Mediavine links in footer branding
- FIX: Fixes issue with Convert Pro popups not displaying when Critical CSS is enabled
- FIX: MV ad hint last unit in sidebar notice fixed
- FIX: MV ad hint sidebar notice fixed
- FIX: Pre-cache links that start with the site url
- FIX: All comments are displayed if Trellis Comments are disabled
- FIX: Disables Critical CSS on WooCommerce Checkout and Cart pages
- FIX: Breadcrumbs will not display on the front page, feed or static
- FIX: Restores Submit button on WooCommerce review page
- FIX: Removed the Critical CSS label from admin bar when in page or post edit mode
- FIX: Clearing Trellis Cache/Upgrading Trellis will now reset "Processing" Critical CSS statuses
- FIX: Thrive Leads mobile content selector
- FIX: Adjusted sizes attribute for post link featured images to allow the browser to select the appropriate image size
- FIX: Fixes layout issues from broken HTML in user comment content
- FIX: Ensures correct title is being added to Critical CSS issues list for category pages
- FIX: PWA version is updated whenever Critical CSS is successful, is purged, or Critical CSS is disabled for a post
- FIX: UI no longer crashes when trying to Queue a page for Critical CSS from the Issues tab
- FIX: Fixes CLS and blurriness for the about widget image on Wisteria and Birch by ensuring the correct source size is used
- FIX: Ensures that All In One SEO settings appear in the Classic Editor for legacy versions of the plugin
- FIX: Data attributes no longer removed from Trellis Setting Hooks fields when settings are rebuilt
- FIX: Adds author 'url' field to json-ld output for type 'person' with Trellis SEO active
- COSMETIC: Adjusts default image sizes attribute to 728px
- CHANGE: Updates Theme URI to the Mediavine Marketplace
- CHANGE: Updates minimum PHP version to 7.2
- CHANGE: Remove 'Enable Additional Image Sizes' setting
- CHANGE: Updates font localization to REST request
- CHANGE: Removes possibility that fonts are served from Google
- CHANGE: Font localization is now a requirement to change fonts
- CHANGE: Button has been added for confirming a custom-typed font
- CHANGE: Sanitization of custom font input
- CHANGE: Adjusts Universal Analytics Field Copy
- CHANGE: Updates privacy parameters for UA tracking disabling both allow_google_signals and allow_ad_personalization_signals
- - REMOVAL: WP Rocket Trellis setting

### 0.15.3 (03/30/2022)

- FEATURE: Images can be eager loaded by adding the `eager-load ` class
- FIX: Fixes issue where image tags with the loading="eager" property were being lazy loaded
- FIX: Adds support for Trellis Images with non-lazyloaded images
- FIX: Critical CSS issues list now display if Critical CSS is turned off due to an issue
- FIX: BTF sidebar localModel position
- FIX: Fixes CLS image aspect ratio issues on posts with broken HTML
- FIX: About Me Widget Images Sizes on specific child themes is fixed
- FIX: Curly brace for an inline style when using Grow Social is no longer missing
- FIX: Fixes issue where image tags with the loading="eager" property were being lazy loaded
- FIX: Trellis will not add meta description nor open graph tags when Grow Social is handling them
- CHANGE: Updated PHP deprecation nag version to 7.2
- CHANGE: Trellis now requires PHP 7.1 or greater
- COSMETIC: Text boxes now appear with a border around them instead of inline text boxes
- COSMETIC: Checkboxes are now easy to see in Customizer Settings
- COSMETIC: Monotext now uses the same font as everything else

### 0.15.2 (02/02/2022)

- FIX: Posts with bad HTML will now still load instead of being a blank page
- FIX: Prevents fatals when checking for Critical CSS on term pages
- FIX: Fixes custom kses allowed elements to not throw warnings after the WordPress 5.9 update
- FIX: Prevents stripping of HTML tags from Footer Copyright Text setting

### 0.15.1 (01/17/2022)

- FIX: Force a critical css purge when updating to 0.15.1

### 0.15.0 (01/17/2022)

- FEATURE: New setting to disable Trellis comments/Jetpack compatibility class
- FEATURE: Add button to with link to Trellis marketplace for settings when no license active
- FEATURE: Added a way to bypass the Trellis lazyload functionality in favor of browser native lazyloading
- FEATURE: Added filter `mv_trellis_about_widget_image_sizes` to adjust About widget thumbnail sizes attribute
- FEATURE: Adds new hooks to be run through the Critical CSS generation lifecycle
- FEATURE: Harmonize color setting inputs with color picker
- FEATURE: Link to the changelog on Trellis Docs added to the theme description, viewable when looking at the theme details
- FEATURE: More/Read More block now works in RSS feeds for RSS feed-driven emails
- FEATURE: New template for Featured post - template-parts/header/header-featured.php
- FEATURE: Update Admin UI, increasing usability of settings with subsections
- FEATURE: Transients are no longer used and replaced with the Throttle API which uses options under the hood
- FIX: About widget thumbnail is no longer lazyloaded
- FIX: About widget thumbnail sizes attribute has been adjusted for its available space
- FIX: Ads will not display on mobile pages when Show Ads on Pages is disabled
- FIX: Category page content is now processed allowing Trellis Images to optimize its images
- FIX: CSS validation errors
- FIX: Disable new WP Rocket delay_js
- FIX: Disabling and Purging Critical CSS on pages set to the Front Page now work
- FIX: Don't show 'Display on mobile devices' option for ATF ad widget
- FIX: EDD no longer causes issues with featured images
- FIX: Feed Ad Spacing setting None value displays correctly in both the Customizer and Settings Page
- FIX: Fixes issue with false negatives about site's REST API support
- FIX: Improve Critical CSS setting language
- FIX: Improves Trellis license checks and caches the status for 12 hours. Includes a button in the Trellis Settings to recheck
- FIX: Made strings translatable where applicable
- FIX: Post Meta Date Display now has the correct default value
- FIX: Prevents multiple WP Fastest Cache menu items from appearing
- FIX: PWA Short name set maxLength, add placeholder text, update copy
- FIX: Remove WP 5.8 `block_categories` deprecated notice
- FIX: Remove Add Media buttons from category description editor because WordPress doesn't support images in category descriptions
- FIX: Removed BTF ad hint/placeholder and added a value for sidebar_btf_selector local model
- FIX: Service worker registration error in rich search results
- FIX: Shows Breadcrumb option in Post Meta Settings only when Yoast breadcrumbs are active and enabled
- FIX: Sidebar is a sibling of main#content for all page types
- FIX: Theme settings will be updated when Mediavine Control Panel is activated and deactivated
- FIX: Underlines added to post content links
- FIX: Updated widget Display on Mobile so it'll work as expected with legacy widgets in the new widget editor
- COSMETIC: .tags-links set to max-width: 100%
- COSMETIC: Hide trellis settings on mobile and add notice
- COSMETIC: Remove License tab from the Customizer
- COSMETIC: Remove plain 'no issues found' box from settings
- COSMETIC: Update disabled license text to button with link to Marketplace Trellis page
LANGUAGE: Updated SEO Setting Copy to reflect expected behavior

### 0.14.4 (10/27/2021)

- FIX: Increases performance of Trellis Comments, reducing server load on pages with numerous comments
- FIX: Fixes smooth scroll conflict with non-Create arrival
- FIX: Prevents the Trellis Settings from crashing if the Google Font settings didn't exist

### 0.14.3 (08/30/2021)

- FIX: Removed Next and Previous text from article navigation. In some cases it was being added to the SERP title.
- FIX: Hooks not migrating properly when upgrading Trellis

### 0.14.2 (08/30/2021)

- COSMETIC: Moved the featured image above the page title on article pagination

### 0.14.1 (08/30/2021)

- FIX: Force the purge of critical css when upgrading Trellis from a version before 0.14.1

### 0.14.0 (08/30/2021)

- FEATURE: New settings for post meta display options.
- FEATURE: Added filter mv_trellis_image_sizes_attribute to allow the Trellis default to be changed
- FEATURE: Added filter mv_trellis_excerpt_image_res for excerpt image resolution size
- FEATURE: Added filter mv_trellis_excerpt_image_sizes for excerpt image sizes attribute
- FEATURE: Added filter mv_trellis_featured_post_image_res for featured post image resolution size
- FEATURE: Added filter mv_trellis_featured_post_image_sizes for featured post image sizes attribute
- FEATURE: Added hook function mvt_aside_before_entry_content that will run tha_aside_before_entry_content just before opening div.entry-content
- FEATURE: Added hook function mvt_aside_after_entry_content that will run tha_aside_after_entry_content just after closing div.entry-content
- FEATURE: Added filter mv_trellis_entry_content_classes for adjusting div.entry-content classes
- FEATURE: Added hook function mvt_trellis_entry_footer_top that will run tha_entry_footer_top just inside the entry footer (footer.entry-footer)
- FEATURE: Added hook function mvt_trellis_entry_footer_bottom that will run tha_entry_footer_bottom just before closing the entry footer tag (footer.entry-footer)
- FEATURE: Added filter mv_trellis_article_nav_image_res for article nav image resolution size
- FEATURE: Added filter mv_trellis_excerpt_image_res for excerpt image resolution size
- FEATURE: Added filter mv_trellis_grow_sidebar_margin_space to adjust side space given to Grow Social sidebar
- FEATURE: Added filter mv_trellis_grow_sidebar_media_query_min_width to adjust min-width to apply side space given to Grow Social sidebar
- FEATURE: Added filter mv_trellis_grow_sidebar_media_query_max_width to adjust max-width to apply side space given to Grow Social sidebar
FEATURE Added filter mv_trellis_grow_sidebar_compatibility_styles to overwrite the styles output when the Grow Social sidebar is active
- FIX: Updated html output to be more semantic
- FIX: Updates the sizes attribute for images to be more specific for Trellis based themes
- FIX: HTML used in the Author Biographical Info displays as expected.
- FIX: mv_trellis_the_title now includes a title for 404s
- FIX: Moved Grow Social specific styles into the compatibility class that will only load when needed
- FIX: Updated scripts for better IE11 support
- FIX: Updated WooCommerce compatibility class to work with semantic changes
- CHANGE: Renamed the filter used to override the article nav image orientation, from mv_trellis_image_orientation to mv_trellis_article_nav_image_orientation
- COSMETIC: Many style updates for the semantic html changes
- COSMETIC: Removed "Cozy" option from Layout Size Trellis Setting
- REMOVED: Bamboo specific styles for Web Stories compatibility

### 0.13.4 (06/14/2021)

- FIX: Removed hook that disabled Yoast json-ld before checking to see if Trellis SEO Output is enabled

### 0.13.3 (06/08/2021)

- FIX: adjusted logic to not output description meta when Trellis SEO Output is disabled

### 0.13.2 (06/08/2021)

- FIX: removed logo inline css that's causing images to not scale as expected

### 0.13.1 (05/26/2021)

- FEATURE: Font CLS fix with settings
- FEATURE: New setting to hide featured images on mobile
- FIX: Sidebar ATF CLS
- FIX: Logo CLS Issue

### 0.13.0 (05/26/2021)

- FEATURE: Adds checks for REST API Availability
- FEATURE: Adds native ad templates and base styles
- FEATURE: Anonymize Google Analytics
- FEATURE: Preload fonts when possible
- FEATURE: Custom CSS that will break in the semantic HTML update is posted to intercom.
- FEATURE: Add touch screen support to desktop menu
- FIX: Remove custom CSS impact from MV Dashboard
- FIX: Remove ad targeting impact from Cloudflare's RocketLoader.
- FIX: WB_REVISION is no longer added to Front Page posts paginated links
- FIX: Site logo/title link URL now has ending slash
- FIX: Default Font is now System Default and warnings are provided for when using a non-web safe font.
- FIX: Moved comment base styles to main style sheet
- FIX: Post navigation images use the Featured Image Size setting for orientation
- FIX: Added role="comment" to comment containers
- FIX: Fix display of fallback user avatars in Safari
- FIX: Fix list style of nested lists
- FIX: License Notice no longer displays 'Invalid Date' on the license's expiration.
- FIX: Critical CSS is no longer generated for WooCommerce pages.
- FIX: If the WP setting 'Comment author must fill out name and email' is disabled, then users can comment without a username or email now.
- FIX: Set THA hooks theme support earlier
- FIX: Added force keep selector to fix Web Story display
- FIX: Trellis Display Settings not Rendering in Customizer
- FIX: Added role="comment" to comment containers
- FIX: All of the hard-coded strings are now using the 'mediavine' text-domain.
- FIX: Excerpt thumbnails should use the correct size
- FIX: High Vulnerability Security Issue is no longer present inside of Critical CSS
- CHANGE: "Comments are closed." notice only displays on posts that have previous comments
- COSMETIC: Improves UX of color selection settings
- COSMETIC: Clean up mobile menu and remove lines
- COSMETIC: Clean up font stack
- COSMETIC: Change normal font name to medium in settings
- REMOVE: Removed Helvetica from the Web Safe font list
- REMOVE: Trellis hooks that were replaced with THA hooks are no longer available

### 0.12.1 (02/25/2021)

- FIX: Constrains the range of inputs allowed by the Critical CSS endpoint.

### 0.12.0 (02/25/2021)

- FEATURE: Added a Critical CSS Issues tab to the Trellis Settings Page
- FEATURE: Changed the text & link on the global error message
- FEATURE: Added multisite support
- FEATURE: More granular control over H tags display
- FEATURE: Adjusts sizes attributes on images to get proper size added during PSI tests.
- FEATURE: Display author name and biographical info on the author page.
- FEATURE: Adds a new "Trellis SEO Output" setting that replaces the old "JSON-LD Source" & "Meta Description Source". JSON-LD, meta description, and open graph are now only output if this setting is ENABLED.
- FIX: .txt files are no longer processed by the service worker
- FIX: Tooltip for the "Display Featured Images" Setting was incorrect
- FIX: tha_head_bottom now fires after wp_head()
- FIX: Critical CSS is no longer generated on the Subscribe to Comments Reloaded page
- FIX: Add a srcset width of 960px to address Google Page Speed Insights warnings about image optimization
- FIX: Update the Instructions for the Footer Copyright Text setting to declare support for HTML
- FIX: Remove resize event listener for sub-menu-open
- FIX: html lang attribute now outputs the Site Language setting value
- REMOVE: Scss and js source files are no longer included as part of the distribution
- REMOVE: custom-functions.php and custom-style.css removed
- COSMETIC: The Trellis settings for Primary and Secondary color are used for the search field border default and focus colors, respectively
- COSMETIC: Removed gutters over 1200px
- COSMETIC: Adds display adjustments for Web Stories

### 0.11.0 (02/25/2021)
- FEATURE: Added Background Accent Color field for customizing the background color of page/post headers
- FEATURE: Theme authors can now use remove_theme_support( 'mv_trellis_background_accent_color' ) to disable support for changing page/post header background colors
- FEATURE: Added filters for the labels & instructions for Theme Settings
- FEATURE: Added theme support attribute to settings schema. Only settings that have theme support or don't declare the need for this attribute will be added to the localized array of settings
- FEATURE: Add a setting for adding third-party service workers
- FEATURE: Adds form validation for invalid hook content
- FIX: moved array of license dependant settings to the back end so they can be filtered by child themes
- FIX: The most recent sticky post will display as the featured post on the home page
- FIX: No longer deferring Thrive Leads frontend javascript
- FIX: Thrive Leads styles needed for interaction after page load will be included in critical css
- FIX: Prevent pixelation of JPG and PNG logos
- FIX: Allow Trellis users to specify Full size images for Featured Image
- FIX: Provide a default for the Featured Image Size field when default_image_ratio isn't populated
- FIX: Adds new method for extracting stored widget values
- FIX: Modified date will not display if it is older than or the same as the published date
- FIX: Change .about-author-title to `<h3>`
- FIX: Added descriptive text to home page sticky excerpt 'Read More' link
- FIX: Removed extra markup from RSS feed
- FIX: Added wp-embed back into our minified script
- FIX: Trellis Settings text fields are now sanitized using `wp_kses`
- REMOVAL: Remove JP2 support from lazyloading
- COSMETIC: removed space for Grow sidebar on screens smaller than 700px
- COSMETIC: Featured Hero background color controlled by Background Accent Color setting

### 0.10.3 (11/25/2020)

- FIX: Added local model selector, content_selector_mobile

### 0.10.2 (11/14/2020)

- FIX: Prevents tha_head_bottom hook from being wrapped in a div

### 0.10.1 (11/11/2020)

- FEATURE: Allow a user to delete all critical CSS files that have been generated (rather than marking them as stale)
- FEATURE: Makes mobile sub-menus open & close with an arrow instead of being always-visible
- FEATURE: Add a setting to prevent meta description conflicts
- FEATURE: Adds settings to set allowlist and force critical CSS options for Critical CSS API
- FIX: Disable some settings if license is invalid
- FIX: Add pagination for articles with multiple pages
- FIX: Add more detail to article meta and set default to display both modified and published dates
- FIX: SCSS variables within calc() are now replaced properly
- FIX: Fix scrolling conflict with WRPM Comment Ratings enabled
- FIX: loading="lazy" will be removed on images that have lazyloading disabled
- FIX: Corrects an issue where "Comments are Closed" message displays on pages
- FIX: No longer adding width/height attribute to externally hosted images
- FIX: Fix comment submission in IE11
- FIX: Renamed filter mv_trellis_css_bypass to mv_trellis_css_allowlist
- FIX: Correctly output Akismet privacy notice in comments
- FIX: Password-protected posts/pages will not request critical css
- REMOVAL: Removes WebP Image Host URL setting
- COSMETIC: Add spacing to <hr/> elements
- COSMETIC: Adjusted spacing around user-entered content

### 0.10.0 (10/26/2020)

- FEATURE: ability to hide the page title on a page that is used as the static home page
- FEATURE: Improve instructions for Trellis License
- FEATURE: Improve instructions for Enable Additional Image Size settings
- FEATURE: Replace color picker component
- FEATURE: delete critical css when adding or removing a primary sidebar widget
- FEATURE: updating a sidebar widget setting invalidates critical css, only applies to the primary sidebar
- FEATURE: Added a Trellis Setting to display the featured image on posts
- FEATURE: Adds data sync for licensed Trellis users
- FEATURE: Adds Intercom widget to settings and customizer for users with valid licenses
- FIX: Meta fields will only show for appropriate post types in Gutenberg editor
- FIX: Fixes JavaScript errors in IE11
- FIX: Prevent JS error on login page
- FIX: Update license warning copy
- FIX: Prevent CLS issues
- FIX: removed add_action instance of `mv_trellis_after_entry`
- FIX: html used in Trellis Settings Hooks will persist changing or upgrading Trellis based themes
- FIX: Fix fetching and updating of comments when using plain permalinks
- COSMETIC: Clean up display of logo, searchbars, and sidebar and footer navs
- COSMETIC: Corrected the display of headers preceding galleries
- COSMETIC: Corrected the image caption overlay display
- COSMETIC: Replaced the search form close `X` with `&times;`
- COSMETIC: Search field input now uses the Trellis Settings Primary Color for its outline/border when it has focus
- COSMETIC: Search toggle icon now uses Trellis Settings Primary Color for its fill and Secondary color when hovered
- COSMETIC: Set body background color to white
- COSMETIC: footer widgets no longer have their text centered by default
- COSMETIC: all li styles within widgets default to list-style:none, margin-left:0, and text-align:left
- COSMETIC: all a styles within widgets default to text-decoration:none, same font size, and text-transform:uppercase
- COSMETIC: updated calendar widget to handle new markup
- COSMETIC: Grow floating sidebar will not cover content on screen widths greater than 700px
- COSMETIC: only display horizontal scrollbar for code when needed
- COSMETIC: comment avatar images will not get squashed on smaller screens

### 0.9.3 (10/12/2020)

- FIX: fixes an issue where Critical CSS behavior depended on Create being active

### 0.9.2 (10/02/2020)

- FEATURE: added a filter for the page title
- FEATURE: plugin compatibility handling framework added
- FEATURE: Checks and validates Trellis Pro license
- FEATURE: added filter mv_trellis_site_title_text_classes for site title markup classes
- FEATURE: added filter mv_trellis_site_title_logo_classes for site logo source markup classes
- FEATURE: added filter mv_trellis_site_title_logo_alt_text for site logo alt text
- FEATURE: Automatically disable Trellis JSON-LD at theme activation if Yoast or AIOSEO exist.
- FEATURE: Add notices for license status
- FEATURE: Add button to remove license
- FIX: Displays a notice on posts when discussion is turned off
- FIX: resolved compatibility issue with Sassy Social Share
- FIX: handle Worth the Read content wrapping compatibility issue
- FIX: Ampersands in author names in comments will render correctly.
- FIX: Prevent display of comments on password-protected pages
- FIX: Critical css will not respond with a WP_Error for critical css Rest API calls
- FIX: Email me whenever Anyone posts a comment is now checked for new comments
- FIX: Fix non-functional buttons in About widget
- FIX: Make sure theme can be previewed on a fresh WordPress installation from the customizer.
- FIX: removed Delay Google Font setting, it's no longer needed
- FIX: removing this htaccess directive in hopes of not conflicting with StackCache
- FIX: Removed some boilerplate code for a React app that never ended up being created.
- FIX: Remove unused CSSComb config
- FIX: Move placement of comment hooks so the content isn't removed on load
- FIX: Remove Genesis hooks from Trellis, preventing duplicate content on plugins that support both Genesis and THA
- FIX: Fix issue where ad hints weren't added within post archives
- COSMETIC: Hide dangerous buttons

### 0.9.1 (09/30/2020)

- FEATURE: Add Trellis Hooks with UI to add custom content
- FEATURE: Add Yoast Breadcrumb support
- FEATURE: added setting to specify which post date(s) are to be displayed in the post meta.
- FEATURE: Add logo optimization filter for Trellis Images to use.
- FEATURE: Add optimized image lazy loading using detection and queueing
- FEATURE: Added a dropdown for setting the post thumbnail orientation
- FEATURE: added a way to handle errors with critical css generation
- FEATURE: Rename "Sidebar Unit" widget to "Mediavine Sidebar Ad Hint" and add usage notices
- FIX: Typography: H1 tags in archives and feeds should be H2 unless it's the page title.
- FIX: article navigation images will not be shown with pinnable images
- FIX: comments will display on pages that have them enabled
- FIX: the menu will not display over the header search form
- FIX: Avoid caching non-200 response types
- FIX: Avoid caching third party JavaScript
- FIX: Fixes an undefined index notice that can occur when a child theme is activated
- FIX: critical CSS generation for static home pages
- FIX: Only displays article schema when on that specific post/page
- FIX: Remove single-size optimized logo sources from Trellis.
- FIX: Activating or updating Trellis based themes will not remove previously localized fonts
- FIX: critical css can handle page slugs with non-english characters and %
- FIX: Home page featured post image will display reliably
- FIX: Enable Additional Image Sizes should work as expected when disabled
- COSMETIC: excerpt title hover uses the selected secondary color.
- COSMETIC: b tag will have the same font-weight as the strong tag
- COSMETIC: ensure the sidebar stays below the header
- COSMETIC: ensure footer is clearing floated elements from the entry content
- COSMETIC: figcaptions will be distinguishable from paragraph text
- COSMETIC: the sidebar should not overlap the content above it anymore

### 0.9.0 (06/10/2020)

- FIX: ad hint widget now has a save setting button for display on mobile
- FIX: don't try to convert svg to webp/jp2
- FIX: moved output of Trellis css variables to before the Trellis css output
- FIX: removed margin from sub menus that pushed it away from its parent
- FIX: Fixes issue where critical CSS wasn't properly generated for static home pages
- FIX: keep the sidebar btf ad from overlapping the footer
- FIX: Adds `mv_trellis_disable_lazy_load_classes` filter to disable image lazy loading based off class name
- FIX: resolved an issue where the secondary css file would be deleted when critical css was rebuilt.
- COSMETIC: added max-width to sidebar widgets to center on narrower screens

### 0.8.3 (05/13/2020)

- FEATURE: Adds native browser lazyloading attribute to iframe tags
- FIX: Adjusts localModel so script wrapper works with third party recipe card plugins
- FIX: Prevents lazyload script from trying to convert gifs to webp/jp2
- FIX: Asynchronously loads secondary CSS
- COSMETIC: Adds space above the sidebar on smaller screens
- COSMETIC: Centers sidebar widgets on small screens

### 0.8.2 (05/05/2020)

- FEATURE: adds Trellis Setting to enable Critical CSS
- FEATURE: add setting to enable/disable PWA, default: enabled
- ENHANCEMENT: Update Workbox Dependencies
- FIX: Fixes about widget image display
- FIX: correct PHP notice in debug logs
- COSMETIC: use new logo for admin theme selector
- COSMETIC: gave long navigation links a little space between wrapped lines

### 0.8.1 (04/29/2020)

- FEATURE: Add option for Pro users to disable Trellis/Mediavine links in footer
- FEATURE: Adds `rel="noopener nofollow"` to Trellis/Mediavine links
- FEATURE: trigger cache clearing when theme update is triggered
- FEATURE: Add sidebar images to lazyload processing
- FEATURE: Disable Yoast and All-In-One SEO options in JSON-LD if these plugins aren't active
- FEATURE: Added two endpoints, mv-trellis/v1/clear-db and mv-trellis/v1/reset-theme for clearing and resetting theme options
- FEATURE: add theme_default to localized settings array
- FIX: added local model defaults
- FIX: added space between links in lists increasing the clickability
- FIX: increased text contrast in multiple places
- FIX: Default JSON-LD to Yoast if Yoast is active when Trellis is activated
- FIX: ColorPicker now displays placeholder Default when it is empty instead of forcing the value to #777.
- COSMETIC: set default Layout Space to 'Cozy'
- COSMETIC: footer widgets are not restricted to 200px wide
- COSMETIC: Adjusted padding on single page header wrapper
- COSMETIC: child theme css isn't enqueued in WP admin

### 0.8.0 (04/14/2020)

- FEATURE: Trellis API updated to V3
- FEATURE: Added detection for Grow social sidebar to add needed body class
- FEATURE: added filter 'mv_trellis_local_script_model' to allow overriding of local model settings
- FEATURE: Adds ability to rollback Rocket settings on activation
- FEATURE: Added additional options to JSON-LD Source field in Customizer
- ENHANCEMENT: when critical css is refreshed, the old css stays in place until the newly rebuild can take its place
- ENHANCEMENT: check critical css file size before it's written to the pub server
- FIX: Critical css is deleted on Trellis based theme switch
- FIX: if disable_critical_css flag is set, get_css_paths will exit early
- FIX: pluralization of "Comments" label when there's a single comment
- FIX: Resolves a console error when loading comments
- FIX: sub-menu UI
- FIX: menu UI in IE11
- FIX: post meta author uses the 'Display name publicly as' user setting
- FIX: site meta description will only be output when Yoast SEO is not active
- FIX: bug with blank customizer page
- FIX: bug where Pro settings wouldn't be available after saving the setting
- FIX: removed the setting that created the footer menu display location
- FIX: Added hook to disable All in One SEO JSON+LD if plugin is enabled
- FIX: Calculates image size attributes faster when lazy loading
- COSMETIC: force videos to 16:9 ratio on mobile
- COSMETIC: Pushed content 65px to left if social sidebar is active
- COSMETIC: Hide Trellis Pro feature settings in the WP Customizer

### 0.7.1 (03/04/2020)

- FEATURE: support for SVGs added
- FEATURE: added check for custom function and custom styles within site root
- FEATURE: added CloudFlare support
- ENHANCEMENT: added php-scoper to help remove scope issues
- ENHANCEMENT: migrated to UI 5.0
- ENHANCEMENT: added hook for running script when theme is updated
- ENHANCEMENT: font selector in Trellis settings updated, size limited with better scrolling
- ENHANCEMENT: font selector in Trellis settings updated, font name displayed in that font

### 0.7.0 (01/16/2020)

- FEATURE: Full width page template added
- ENHANCEMENT: Heading Font setting accepts custom font(s)
- ENHANCEMENT: add theme slug to body class
- ENHANCEMENT: added 3 action hooks to footer: mv_trellis_before_footer, mv_trellis_footer, mv_trellis_after_footer
- ENHANCEMENT: new shortcodes: mv_trellis_footer_backtotop, mv_trellis_footer_copyright, mv_trellis_footer_childtheme_link, mv_trellis_footer_trellis_link, mv_trellis_footer_medivine_link, mv_trellis_footer_wordpress_link, mv_trellis_footer_site_title
- ENHANCEMENT: footer copyright line is built using the new shortcodes
- ENHANCEMENT: Site logo placed within a picture element
- ENHANCEMENT: added bypass to specify css classes that need to be included in the critical draw
- ENHANCEMENT: expanded webp and jp2 server support
- ENHANCEMENT: updated htaccess entry for support of the following: woff, woff2, webp, jp2
- FIX: renamed Theme class to Init, better reflecting what it does
- FIX: font sizes for content is properly set based on the Trellis setting
- FIX: adjusted lazyload script match regex - replaces end of url matches, not all matches
- FIX: Fix blank page when navigating from Trellis settings to Customizer
- COSMETIC: many css tweaks
- COSMETIC: Automatic case correction for Mediavine

### 0.6.0 (12/09/2019)

- FEATURE: use picture element for site logo
- FEATURE: Google font localization. Selected Google fonts will be served from the site
- ENHANCEMENT: web safe fonts are marked as such and listed first in theme options
- ENHANCEMENT: when a search has no results, display most recent posts under the 'No results' statement.
- ENHANCEMENT: gutter sizes are filterable for Layout Space option
- ENHANCEMENT: added option to widgets that will allow them to be hidden on smaller screens
- ENHANCEMENT: added option for default image size ratio
- ENHANCEMENT: added data-pin-attribute to images with original image src
- ENHANCEMENT: added footer copyright filter
- ENHANCEMENT: description on how to use settings api added to readme
- ENHANCEMENT: many updates to lazyloading images
- FIX: navigation items wrap
- FIX: menu item names don't break mid-word
- FIX: cache namespaces
- FIX: removed link from Posted on date for single posts
- FIX: removed hardcoded footer navigation location
- FIX: CI tests that were failing due to WP svn rate limits
- FIX: IE support for picture elements
- COSMETIC: many css tweaks
- COSMETIC: removed mobile specific widget area

### 0.5.1 (11/08/2019)

- FIX: Remove extra div tag from article content

### 0.5.0 (11/07/2019)

- ENHANCEMENT: css tweaks
- ENHANCEMENT: added search bar to header replacing the mobile search bar
- ENHANCEMENT: added setting for adjusting element spacing
- ENHANCEMENT: added setting for logo size
- ENHANCEMENT: better cache clearing
- ENHANCEMENT: better support for rocket cache
- ENHANCEMENT: better custom font stack support
- ENHANCEMENT: added fallbacks for Google fonts
- ENHANCEMENT: added post meta to single post header
- ENHANCEMENT: added custom title option for category archive list
- ENHANCEMENT: added custom title option for author archive list
- FIX: long words not breaking and extending outside of the container
- FIX: support for IE11
- FIX: error caused by old version of LIBXML on server

