---
title: "Trellis Benefits"
type: docs
weight: 20
description: >
  Improve Core Web Vitals metrics, offer Progressive Web Apps (PWAs), and more when you use Trellis as your theme framework.
---
Trellis and its helper plugins can replace image generators, HTML/CSS/JavaScript optimizers, and other WordPress plugins (or it can work beside some of your favorite ones). You can refer to our [Conflicts and Compatibilities](https://intercom.help/mediavine-products/en/articles/5046317-trellis-themes-conflicts-and-compatibilities) article for detailed information. Here’s a summary of Trellis’ main features:
## For Publishers

- **Better Core Web Vitals metrics:** Trellis automates key components to raise a site’s Core Web Vitals scores. First Input Delay (FID), Cumulative Layout Shift (CLS), and Largest Contentful Paint (LCP) measurements all improve when using Trellis. Better Core Web Vitals metrics boost a site’s ranking with Google.
- **Image size optimization:** Trellis tells WordPress to generate additional image sizes that are more commonly used. Properly sized images load faster, look better, and reduce warnings in Google Page Insights.
- **Built-in Mediavine ad integration:** Functions in Trellis automate the placement and sizing of Mediavine ads. A Mediavine Sidebar Ad widget lets publishers utilize the upper sidebar ad unit, and Trellis also provides a default HTML structure for optimal desktop and sidebar ad display.
- **Progressive Web App (PWA) support:** Trellis includes the necessary pieces to offer a PWA to visitors. Sites can be installed like an app on a mobile or desktop device without a publisher paying for native app development.

## For Developers

- **Optimized CSS:** Trellis’ Critical CSS feature creates two separate, optimized CSS files: one for initial viewport content, and another for the rest. When a reader visits a page, Trellis serves the initial viewport stylesheet as inline styles—the other is loaded after as a linked stylesheet, resulting in faster page rendering. Learn more about Critical CSS in our Advanced Topics section or in our [Working with Critical CSS](https://intercom.help/mediavine-products/en/articles/4551189-working-with-critical-css) Help Center article.
- **Service worker integration:** Trellis uses [service workers](https://developers.google.com/web/fundamentals/primers/service-workers) to cache assets in the browser, reducing the need for network round trips.
- **Better SEO with JSON-LD:** Trellis generates structured data for search engines in the JSON-LD format (preferred by Google). This improves page indexing and supports displaying rich snippets in search results.
- **JavaScript enhancements:** Trellis minifies JavaScript files and defers loading asynchronously. This prevents render blocking and serves up pages faster.
- **Template caching:** Trellis caches paths to template files, providing an immediate performance boost. No need for WordPress to do repeated template lookups.
- **REST API-based comments:** When using Trellis Comments, only the first five will initially render. Additional comments appear when the user scrolls to the comments section.
- **Font localization:** Trellis localizes specific Google Fonts. This speeds up font loading in the browser and keeps site visitor data from being sent to the Google Fonts API.
- **Lazy-loaded images:** Trellis lazy loads all images and iframes even for browsers that don’t natively support it.

## What’s Next?

- See what [Add-Ons]({{< ref "add-ons" >}}) come with Trellis
- [Get started]({{< ref "/getting-started" >}}) creating a Trellis child theme
- Implement Trellis’ features in your own code in the [Advanced Topics]({{< ref "/advanced-topics" >}}) section