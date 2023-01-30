---
title: "Wisteria"
type: no_toc
weight: 40
description: >
  A list of changes made to the Wisteria child theme.
---

## Changelog

### 1.0.1 (11/09/2022)
FIX: Fixes issue where large horizontal logos were constraining the header navigation area
FIX: Fixes CLS issue after Critical CSS is generated

### 1.0.0 (10/26/2022)
- FEATURE: Adds theme support for "Hide page title" setting to Wisteria
- FIX: Prevents issue where [Grow.me](http://grow.me/) carousel and sticky sidebar would overlap
- FIX: Title before `.trellis-comments` fixed for html entities like `&`
- FIX: Resolves Logo CLS
- FIX: Solves desktop sidescroll caused by sub-menu of final menu-item
- FIX: CLS caused by the logo on desktop is resolved
- FIX: Fix CLS caused by `.header-container`
- FIX: Resolve css validation errors
- FIX: For better mobile results, make `.search-field` width a calculation
- FIX: Ensures links are bold when anchor tag is child of a `strong` or `b` tag
- FIX: Removes redundant layout setting notice
- FIX: Prevents 2nd-level submenu overlap
- FIX: Sets `max-width` for post tags
- FIX: Fixes WP Block buttons so they have vertical margin when stacked
- FIX: Centers mobile logo when search icon is disabled
- CHANGE: Updates Theme URI to the Mediavine Marketplace

### 0.8.0 (08/23/2021)
- FEATURE: Transitional code added for backwards compatibility until Trellis 0.14.x is released
- FEATURE: Sidebar breakpoint is now added to the local model for use by the web wrapper
- FEATURE: Implement Trellis Heading Settings from Trellis Core
- FEATURE: New Post Meta Settings that allow for choice of meta placement on posts
- FIX: Hide widgets when toggled for mobile/tablet
- FIX: Critical CSS Status Bar now gives a status
- FIX: Updates the sizes attribute for images to be more specific for Trellis based themes
- FIX: Grow Social Sidebar is now accounted for in styling
- FIX: Updated HTML output to be more semantic
- FIX: Hero Image on home page
- COSMETIC: Update Web Stories archive page style
- COSMETIC: Many style updates for the semantic HTML changes
- COSMETIC: Removed "Cozy" option from Layout Size Trellis Setting
- COSMETIC: Changed desktop menu submenu pop out direction for last two menu items
- COSMETIC: Removed lines from mobile menu

### 0.7.0 (03/08/2021)
- FEATURE: Background accent color setting added
- FIX: Main nav style being applied to footer widget menu
- FIX: Full page selector refined to fix padding between sidebar and content
- COSMETIC: Add form styling
- COSMETIC: Move logo up into header on home tablet/mobile
- COSMETIC: Above the fold for mobile/tablet: tighten meta area
- COSMETIC: Above the fold for mobile/tablet: tighten logo area set to 75px high
- COSMETIC: Change comments to overflow-x: auto

### 0.6.0 (11/24/2020)
- FEATURE: Add mobile submenu toggle actions
- FIX: Sidebar selector name fixed.
- FIX: Right margin fixed on desktop.
- FIX: Search-toggle separated from search-form so search-toggle JS works again
- FIX: Full width pages and remove gutters over 1200px
- FIX: Figcaption style and remove variable gutter from the top/bottom of content images
- FIX: Harmonize fonts on nav, title, search-field, button and select

### 0.5.1 (11/16/2020)
- FIX: Tiny phone gutters reduced to 10px to accommodate ads in 320px display
- FIX: Menu navigation carrot removed on desktop menu
- FIX: Article meta and titles wrap on desktop
- FIX: Fixes layout of archive pages when hooked content is added

### 0.5.0 (11/16/2020)
- FIX: remove full width mix-in
- FIX: Full page audit. Sidebar set to 360px and ads always 300px.
- FIX: Set taxonomy description to 100% width

### 0.4.0 (10/27/2020)
- FIX: remove erroneous border-radius on #content img
- FIX: Set .archive-heading bottom-margin to zero.
- FIX: SCSS variables within calc() are now replaced properly
- FIX: over ride mixin for menu background on widgets
- FIX: removed lazyload class from primary sidebar container
- COSMETIC: update the screenshot.png
- COSMETIC: Set category selector to full width

### 0.3.0 (05/06/2020)
- COSMETIC: many style updates

### 0.2.0 (04/14/2020)
- FEATURE: added mv_trellis_footer hook for handling the footer area
- FEATURE: added mv_trellis_before_footer and mv_trellis_after_footer hooks to the footer for before and after the footer area
- FIX: sub-menu UI
- FIX: site meta description will only be output when Yoast SEO is not active
- FIX: added theme detail section to style.css
- FIX: function to add the theme name to the body class list has been moved to Trellis
- COSMETIC: many style updates

### 0.1.0 (11/07/2019)
- Initial release