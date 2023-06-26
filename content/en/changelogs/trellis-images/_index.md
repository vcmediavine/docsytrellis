---
title: "Trellis Images"
type: no_toc
weight: 50
description: >
  A list of changes made to the Trellis Images plugin.
---

## Changelog

### 0.7.1 (04/25/2023)

- FIXED: Added a comma to the logo source tag's srcset attribute. The first image URL in the srcset was missing a comma, which could result in a blurred image.

### 0.7.0 (04/03/2023)

- NEW: Trellis Images 0.7.0 now requires a minimum version of Trellis 0.18.0 and a minimum PHP version of 7.3 to run.
- NEW: Swapping legacy images for WebP versions is now handled by Trellis Images. Previously, Trellis Images only produced new WebP images while Trellis Core handled the swapping functions.
- NEW: Added a new mv_trellis_images_stop_process filter to terminate image processing.
- NEW: Added a link to the Mediavine Marketplace in the Trellis Images plugin page.
- CHANGED: Added the ability to serve a WebP version of a specific image size if it already exists. Previously, all image sizes had to be converted before a WebP version was served.
- FIXED: Added code to exclude WebP processing for images hosted on a CloudFlare CDN (these are recognized by cdn-cgi in the URL). Previously, images would appear broken after processing due to how CloudFlare operates.

### 0.6.0 (05/26/2021)

- FEATURE: Trellis Images no longer uses transients for throttling.
- FIX: A logo with an optimized src but no srcset will now be swapped to use its webp version.

### 0.5.0 (04/26/2021)
- FEATURE: Disabling the plugin will also now clear the optimization queue from the WordPress event cron.
- FIX: If an image in the queue has already been optimized, the queue will be cleared automatically. This prevents fixated ("stuck") optimization requests. (#133)

### 0.4.5 (04/26/2021)
- FEATURE: Added a workaround where disabling & re-enabling the plugin will clear "stuck" throttle on image optimization request speed. (#115)
- FIX: A technically invalid URL in an image srcset attribute could cause no image to display on mobile. (#121)
- FIX: A missing or broken image srcset attribute was sometimes causing an on-page warning. (#119)

### 0.4.4 (04/26/2021)
- FIX: Fatal error if logo had an empty HTML attribute. (#114)

### 0.4.3 (09/30/2020)
- FIX: When optimization queue was locked, optimized images would not load on front end. (#100)

### 0.4.1 (09/30/2020)
- FIX: Add a conservative queuing limit & throttling system for image processing.
- REMOVE: Disable `jp2` image generation.

### 0.4.0 (09/30/2020)
- FEATURE: Images will now be optimized asynchronously via cron. Both jp2 and webp variants will be generated for every image currently used in each post and substituted at pageload by the Trellis theme. IMPORTANT: It may take several minutes to process a new article. On sites with caching, the image optimizations would not be seen until the next cache break afterward. When initially enabling this plugin, it may take many hours for it to update the entire site (to avoid overloading the server or causing timeouts). It should (on average) naturally prioritize articles with higher traffic.
- FEATURE: Image URLs contained in the srcset will now be processed in the optimizer the same as image src.
- FEATURE: Images will only be marked as optimized for the frontend (with the data-{type} attribute) if all the srcset URLs have also been parsed.
- FEATURE: Add `srcset` support for logo optimization using `webp` and `j2`.
- FIX: Security improvements for API connections and file system use.
- FIX: Move the API timeout to a constant and decrease it from 3 seconds to 1 second. Overall worst-case scenario therefore lowers from 15 seconds (3 sec x 5 images) to 5 seconds.

### 0.3.1 (05/05/2020)
- FIX: replace double slashes with single in the image path sent to Trellis API

### 0.3.0 (04/27/2020)
- FEATURE: use trellis-api to fetch images

### 0.2.2 (03/24/2020)
- FIX: Improve server compatibility

### 0.2.1 (01/16/2020)
- FIX: link up kernl for updates

### 0.2.0 (01/16/2020)
- FIX: Make sure we have directory permission to write to the images when checking server support
- FIX: Explicitly set a 200 status when returning an image