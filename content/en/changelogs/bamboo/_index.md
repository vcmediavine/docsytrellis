---
title: "Bamboo"
type: no_toc
weight: 20
description: >
  A list of changes made to the Bamboo child theme.
---

## Changelog

### 1.0.0 (10/05/2022)
- FEATURE: Adds link to public changelog in theme details
- FEATURE: Adds support for Trellis tha_content_header_after hook
- FEATURE: Adds theme support for "Hide page title" setting (requires core Trellis 0.17.0)
- FIX: Constrains maximum width of tag links to content area
- FIX: Increases full width page template from 728px to 1200px wide on desktop
- FIX: Adds underlines to all links in post content to improve accessibility
- FIX: Fixes nested duplicate media query
- FIX: Solves desktop sidescroll caused by sub-menu of final menu-item
- FIX: Adds mvt_title_before() to static front page template before page title output
- FIX: Adds mvt_title_after() to static front page template after page title output
- FIX: Removes redundant layout setting notice
- FIX: Fixes nested submenu to work like Trellis Core on mobile
- Fix: Remove colon in header author meta after word 'By'
- COSMETIC: Reduces the padding between the heading and post content
- COSMETIC: Updates the screenshot preview that appears in Appearance -> Themes
- CHANGE: Removes unneeded Mediavine ad hint div from markup
- CHANGE: Updates Theme URI to the Mediavine Marketplace

### 0.6.2 (08/23/2021)
- FIX: Removed Next and Previous text from article navigation. In some cases it was being added to the SERP title.

### 0.6.1 (08/23/2021)
- FIX: Transitional code is now returning the filtered local model after adding the sidebar breakpoint value

### 0.6.0 (08/23/2021)
- FEATURE: Transitional code added for backwards compatibility until Trellis 0.14.x is released
- FEATURE: Add support for Trellis Heading Control
- FEATURE: Customized the sidebar_minimum_width local model value for Bamboo
- FEATURE: Add support for Trellis Post Meta display selections
- FIX: Updated html output to be more semantic
- FIX: Adjusted the orientation and resolution requested for Featured Post and Excerpt images
- FIX: Adjusted the sizes attribute for Featured Post and Excerpt images
- FIX: Hide widgets when Display on Mobile is not checked
- FIX: Updated styles for Critical CSS status on WP admin bar
- COSMETIC: Updated the header and post meta sections to 'lift' content higher on the pages/posts
- COSMETIC: Many style updates for the semantic html changes
- COSMETIC: Removed "Cozy" option from Layout Size Trellis Setting
- REMOVED: Specific styles for Web Stories compatibility

### 0.5.1 (05/26/2021)
- FIX: Removed hardcoded font family Roboto Slab

### 0.5.0 (03/08/2021)
- FIX: Moved the before content hook to the correct place
- FIX: Correct function is now used just before the header container
- COSMETIC: Reduced font sizes, margins, and padding to 'lift' more content into view on smaller screens
- COSMETIC: Trellis font-size setting is now applied to excerpt contents

### 0.4.0 (11/30/2020)
- FIX: No longer hiding the date last updated on posts using css
- FIX: Fix hero image size on tiny phone
- COSMETIC: Adjusted the Navigation Menu widget sub-menu indentation
- COSMETIC: Updated the styles for widgets that display their output as a list
- COSMETIC: Updated dropdown/select field styles
- COSMETIC: Updated the styles for the primary menu for smaller screens
- COSMETIC: Updated the styles for the sub-menu toggle icons
- COSMETIC: Added padding to keep the Grow floating sidebar from covering content
- COSMETIC: Fixes appearance of radio buttons

### 0.3.0 (10/27/2020)
- FEATURE: Add support for Trellis Hooks UI to add custom content
- FIX: Added child_slug to child theme options. This is used for identification and added to the body class
- FIX: added max-width for iframe to keep in from expanding outside its parent container
- COSMETIC: body background and color properties have been updated to use `#fff` and `#1e1e1e` respectively
- COSMETIC: updated the styles of the following html tags: code, pre, blockquote, pullquote, and cite
- COSMETIC: added styles to display Jetpack galleries properly

### 0.2.0 (06/17/2020)
- FIX: add svg logo support
- COSMETIC: removed image grayscale filter from excerpt featured and the about widget images
- COSMETIC: adjusted the side margin/padding for screens below 380px to give ads more room
- COSMETIC: cleaned up menu margins

### 0.1.0 (04/14/2020)
- initial release