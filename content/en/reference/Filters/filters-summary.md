---
tags: ["filters"]
title: "Filters Summary"
weight: 20
type: no_toc
description: >
  An alphabetically-sorted list of available filters in Trellis, showing only the filter name and description. Click on a filter name for detailed information.
---
### [mvt_processing_css_status_timeout](../filters-detail#mvt_processing_css_status_timeout)

Sets the timeout period for the Processing state in Critical CSS.

------

### [mvt_requires_default_wp_fields](../filters-detail#mvt_requires_default_wp_fields)

Determines whether default WordPress comment fields should be used in the `comments_form` call in comments.php. If Trellis Comments are enabled, WordPress comment fields are not used.

------

### [mv_trellis_about_widget_image_height](../filters-detail#mv_trellis_about_widget_image_height)

Applied to the height attribute on the About Widget `<img>` tag.

------

### [mv_trellis_about_widget_image_width](../filters-detail#mv_trellis_about_widget_image_width)

Applied to the width attribute on the About Widget `<img>` tag.

------

### [mv_trellis_about_widget_image_size](../filters-detail#mv_trellis_about_widget_image_size)

The registered size to be used for the About Widget image. This can be a Trellis image size, a WordPress image size, or a custom size.

------

### [mv_trellis_about_widget_image_sizes](../filters-detail#mv_trellis_about_widget_image_sizes)

Applied to the sizes attribute value for the About Widget thumbnail.

------

### [mv_trellis_admin_runtime_dependencies](../filters-detail#mv_trellis_admin_runtime_dependencies)

Lists the registered dependencies needed for the mv-trellis/runtime script.

------

### [mv_trellis_allowed_google_fonts](../filters-detail#mv_trellis_allowed_google_fonts)

Returns a list of allowed Google Fonts to be supplied to Body Font and Heading Font settings. Array keys are the labels provided to the settings and the values are the CSS values.

------

### [mv_trellis_allowed_non_google_fonts](../filters-detail#mv_trellis_allowed_non_google_fonts)

Returns a list of web safe fonts to be supplied to Body Font and Heading Font settings. Array keys are the labels provided to the settings and the values are the CSS values.

------

### [mv_trellis_always_scan_template_files](../filters-detail#mv_trellis_always_scan_template_files)

Determines if the Trellis template part files should be scanned on every page load. When set to False, Trellis will only scan template part files upon activation, update, or when clearing the Trellis cache.

------

### [mv_trellis_article_nav_image_orientation](../filters-detail#mv_trellis_article_nav_image_orientation)

Applies the image orientation for post navigation images.

------

### [mv_trellis_article_nav_image_res](../filters-detail#mv_trellis_article_nav_image_res)

Applies the resolution to be used for the post navigation image size.

------

### [mv_trellis_async_styles_ignore](../filters-detail#mv_trellis_async_styles_ignore)

A list of filepaths to ignore from asynchronous stylesheet loading on the site’s front-end.

------

### [mv_trellis_base_gutters](../filters-detail#mv_trellis_base_gutters)

Applies to the base gutter sizes used for layout spacing. A value (in pixels) represents the amount of space to apply between layout elements. Uses the Layout Space setting in the Mediavine Trellis Dashboard.

------

### [mv_trellis_before_update_{$setting['slug']}](../filters-detail#mv_trellis_before_update_settingslug)

Filters a Trellis setting before updating it in the options table. This provides a way to trigger an action before the value is saved.

For example, when changing the featured image size, a developer might want to make sure all of the image sizes used in the srcset are generated.

------

### [mv_trellis_childtheme_link_shortcode](../filters-detail#mv_trellis_childtheme_link_shortcode)

Applies the HTML string for the link to the child theme. If the Hide Footer Links setting is off, Trellis will display a link to the child theme in the footer.

------

### [mv_trellis_comments_template](../filters-detail#mv_trellis_comments_template)

The path to the comments template file. Defaults to an empty string so that the comments.php file from the theme is loaded.

------

### [mv_trellis_copyright_shortcode](../filters-detail#mv_trellis_copyright_shortcode)

HTML string for the copyright information shown in the footer.

------

### [mv_trellis_crit_css_min_file_size](../filters-detail#mv_trellis_crit_css_min_file_size)

Specifies the minimum size (in bytes) required to save a Critical CSS file. If the generated Critical CSS for a post or page is below this threshold, Trellis will not create a Critical CSS file.

------

### [mv_trellis_critical_css_rate_limit_in_seconds](../filters-detail#mv_trellis_critical_css_rate_limit_in_seconds)

Applies the rate (in seconds) of calls to the Trellis Critical CSS API when generating critical CSS files.

------

### [mv_trellis_critical_css_timeout_in_seconds](../filters-detail#mv_trellis_critical_css_timeout_in_seconds)

Applies the Critical CSS request timeout duration. After this time, if a request has not been answered, it will timeout.

------

### [mv_trellis_css_allowlist](../filters-detail#mv_trellis_css_allowlist)

Applies a list of CSS selectors that will be kept in the Non-Critical CSS file. Partial selector names can be passed in the array to designate multiple selectors.

------

### [mv_trellis_css_force_keep](../filters-detail#mv_trellis_css_force_keep)

Applies a list of CSS selectors to be kept in the Critical CSS file. Partial selector names can be passed in the array to designate multiple selectors.

------

### [mv_trellis_css_vars](../filters-detail#mv_trellis_css_vars)

Applies the available CSS variables for styling. Returns an array of CSS variables in ‘name’ => 'value' format.

------

### [mv_trellis_default_featured_image_size](../filters-detail#mv_trellis_default_featured_image_size)

Applies the slug of the image size to be used as the featured image size. Defaults to the value of the Featured Image Size setting in the Mediavine Trellis Dashboard.

------

### [mv_trellis_disable_add_async_attribute](../filters-detail#mv_trellis_disable_add_async_attribute)

Disables asynchronous loading on all enqueued scripts.

------

### [mv_trellis_disable_convert_iframe_to_lazyload_when_enabled](../filters-detail#mv_trellis_disable_convert_iframe_to_lazyload_when_enabled)

Disables adding “loading=lazy” attribute to iframes.

------

### [mv_trellis_disable_convert_image_to_lazyload_when_enabled](../filters-detail#mv_trellis_disable_convert_image_to_lazyload_when_enabled)

Disables adding “loading=lazy” attribute to images. 

------

### [mv_trellis_disable_lazy_load_classes](../filters-detail#mv_trellis_disable_lazy_load_classes)

An array of class names on image tags that will disable lazy loading for an image.

------

### [mv_trellis_disable_og_plugin_slugs](../filters-detail#mv_trellis_disable_og_plugin_slugs)

An array of plugin slugs that will disable Trellis Open Graph output if any are active.

------

### [mv_trellis_disable_process_images](../filters-detail#mv_trellis_disable_process_images)

Disables processing of all image optimizations.

------

### [mv_trellis_disable_{$this->slug}_compatibility](../filters-detail#mv_trellis_disable_this-slug_compatibility)

Disables compatibility code for the specified plugin slug. Compatibility code is written by Mediavine and corresponds to plugins listed in Trellis’ compatibility directory (mediavine-trellis/inc/compatibility).

------

### [mv_trellis_disable_set_image_cls_aspect_styles](../filters-detail#mv_trellis_disable_set_image_cls_aspect_styles)

Disables adding inline aspect ratio styles.

------

### [mv_trellis_disable_set_image_data_pin_attribute](../filters-detail#mv_trellis_disable_set_image_data_pin_attribute)

Disables adding data-pin-media attribute to images. Allows specifying an alternate version of an image for Pinterest.

------

### [mv_trellis_disable_set_image_dimensions](../filters-detail#mv_trellis_disable_set_image_dimensions)

Disables setting image width and height attributes on all images.

------


### [mv_trellis_enable_lazy_load](../filters-detail#mv_trellis_enable_lazy_load)

Determines whether lazy loading is enabled for images and iframes.

------

### [mv_trellis_enqueue_child_style](../filters-detail#mv_trellis_enqueue_child_style)

Determines whether the child theme style should be enqueued.

------

### [mv_trellis_enable_js_optimizations](../filters-detail#mv_trellis_enable_js_optimizations)

Determines if JavaScript optimizations are enabled. This is used by compatibility classes for JavaScript optimization plugins. Defaults to True but will read the value of the Trellis setting in the Mediavine Trellis Dashboard.

------

### [mv_trellis_entry_content_classes](../filters-detail#mv_trellis_entry_content_classes)

List of CSS classes added to the entry-content `<div>`.

------

### [mv_trellis_excerpt_image_res](../filters-detail#mv_trellis_excerpt_image_res)

The resolution to be applied when getting the excerpt image size. Trellis includes the options of high, med_high, med, and low.

------

### [mv_trellis_excerpt_image_sizes](../filters-detail#mv_trellis_excerpt_image_sizes)

Applies the sizes attribute to excerpt thumbnail images.

------

### [mv_trellis_featured_post_image_res](../filters-detail#mv_trellis_featured_post_image_res)

The resolution to be used when getting the featured post thumbnail image. Trellis includes the options of high, med_high, med, and low.

------

### [mv_trellis_featured_post_image_sizes](../filters-detail#mv_trellis_featured_post_image_sizes)

The featured post image sizes attribute.

------

### [mv_trellis_filter_localized_font_types](../filters-detail#mv_trellis_filter_localized_font_types)

Specifies which font types/formats are allowed to be localized.

------

### [mv_trellis_flags](../filters-detail#mv_trellis_flags)

An array of flags that Trellis will look for in the submitted URL. Uses the `mvt_flags` query parameter.

------

### [mv_trellis_force_disable_critical_css](../filters-detail#mv_trellis_force_disable_critical_css)

Stops Critical CSS requests.

------

### [mv_trellis_footer_copy_text](../filters-detail#mv_trellis_footer_copy_text)

Sets the footer copyright text before being passed to `mv_trellis_copyright_shortcode`.

------

### [mv_trellis_get_{$post_type}_meta_fields](../filters-detail#mv_trellis_get_post_type_meta_fields)

Applies the Trellis meta fields for a specific post type.

------

### [mv_trellis_google_font_style_{$font_type}_default](../filters-detail#mv_trellis_google_font_style_font_type_default)

Applies the default font styles to use for a particular type of Google Font.

------

### [mv_trellis_google_font_style_{$font_type}_{$sanitized_font_name}](../filters-detail#mv_trellis_google_font_style_font_type_sanitized_font_name)

Applies the font styles for a specific Google font.

------

### [mv_trellis_grow_sidebar_compatibility_styles](../filters-detail#mv_trellis_grow_sidebar_compatibility_styles)

Used to add to or replace custom styles for Grow Social when the plugin is active.

------

### [mv_trellis_grow_sidebar_margin_space](../filters-detail#mv_trellis_grow_sidebar_margin_space)

Adjusts the sidebar margin space for the Grow Social sticky sidebar when the plugin is active. Helps to prevent Grow Social from covering content.

------

### [mv_trellis_grow_sidebar_media_query_min_width](../filters-detail#mv_trellis_grow_sidebar_media_query_min_width)

Allows child themes to adjust the minimum viewport width for when the Grow Social styles are active.

------

### [mv_trellis_grow_sidebar_media_query_max_width](../filters-detail#mv_trellis_grow_sidebar_media_query_max_width)

Allows child themes to adjust the maximum viewport width for when the Grow Social styles are active.

------

### [mv_trellis_hierarchy](../filters-detail#mv_trellis_hierarchy)

The array of file names to use when searching for template parts, in hierarchy of search order.

------

### [mv_trellis_image_orientation](../filters-detail#mv_trellis_image_orientation)

Specifies the article nav image orientation. This is the image size passed to `mv_trellis_get_attachment_image_tag`. Defaults to the value of the Featured Image Size setting in the Mediavine Trellis Dashboard.

------

### [mv_trellis_image_sizes](../filters-detail#mv_trellis_image_sizes)

A list of theme images sizes in a key/value format. These options are passed to the Featured Image Size setting in the Mediavine Trelllis Dashboard. The array should contain a label key with the value shown in the user interface, and a value key with the slug.

------

### [mv_trellis_image_sizes_attribute](../filters-detail#mv_trellis_image_sizes_attribute)

Adjusts the Trellis sizes attribute for an image.

------

### [mv_trellis_js_plugin_name](../filters-detail#mv_trellis_js_plugin_name)

Displays the plugin name responsible for disabling JavaScript optimizations.

------

### [mv_trellis_license_required_settings](../filters-detail#mv_trellis_license_required_settings)

An array of settings dependent on a Trellis license.

------

### [mv_trellis_link_shortcode](../filters-detail#mv_trellis_link_shortcode)

HTML string for the link to the Trellis homepage that appears in the site footer.

------

### [mv_trellis_local_script_model](../filters-detail#mv_trellis_local_script_model)

Allows overriding of the Mediavine Control Panel (MCP) ad settings for the script wrapper.

------

### [mv_trellis_logo_sources](../filters-detail#mv_trellis_logo_sources)

Allows Trellis Images to offer an optimized image version via source tags.

------

### [mv_trellis_match_image_dimensions](../filters-detail#mv_trellis_match_image_dimensions)

Determines if Trellis should check that dimensions match the registered image size.

------

### [mv_trellis_mediavine_link_shortcode](../filters-detail#mv_trellis_mediavine_link_shortcode)

HTML string for the link to the Mediavine homepage in the site footer.

------

### [mv_trellis_memory_exceeded](../filters-detail#mv_trellis_memory_exceeded)

Returns whether Trellis has exceeded its memory limit. Returns False if the memory limit has not been reached. Memory limit is set via `mv_trellis_memory_limit_percent`.

------

### [mv_trellis_memory_limit_percent](../filters-detail#mv_trellis_memory_limit_percent)

Sets the percentage of available WordPress memory as a decimal. Trellis uses this amount to determine if there is enough memory available for its batch processes.

------

### [mv_trellis_model_sidebar_breakpoint](../filters-detail#mv_trellis_model_sidebar_breakpoint)

Adjusts the value added for the sidebar breakpoint. This is used by the Mediavine ad script wrapper so that ads are not served when the sidebar is pushed below the content.

------

### [mv_trellis_nonasync_js_handles](../filters-detail#mv_trellis_nonasync_js_handles)

List of handles where Trellis should not load scripts asynchronously. Should match handles passed to `wp_register_script`.

------

### [mv_trellis_nonasync_js_urls](../filters-detail#mv_trellis_nonasync_js_urls)

List of script source URLs that Trellis should not load asynchronously.

------

### [mv_trellis_nonasync_js_prefixes](../filters-detail#mv_trellis_nonasync_js_prefixes)

List of handle prefixes where Trellis should not load scripts asynchronously. Prefixes should be at the start of the handles passed to `wp_register_script`.

------

### [mv_trellis_pages_pagination_args](../filters-detail#mv_trellis_pages_pagination_args)

Arguments to be passed to `the_posts_pagination`. Available arguments are described on the [WordPress paginate_links function page](https://developer.wordpress.org/reference/functions/paginate_links/)**.**

------

### [mv_trellis_post_link_featured_image_sizes](../filters-detail#mv_trellis_post_link_featured_image_sizes)

Outputs the sizes attribute in featured image post links.

------

### [mv_trellis_process_content](../filters-detail#mv_trellis_process_content)

Returns the DOM document to make changes before it’s output to the browser.

------

### [mv_trellis_resolution_sizes](../filters-detail#mv_trellis_resolution_sizes)

List of resolution sizes to associate with image sizes.

------

### [mv_trellis_settings](../filters-detail#mv_trellis_settings)

Used to add or modify theme settings whenever the settings are being built or rebuilt. A Flags key can be used to force a value update to the default.

------

### [mv_trellis_settings_groups](../filters-detail#mv_trellis_settings_groups)

Used to add or modify theme setting groups or tabs.

------

### [mv_trellis_settings_update](../filters-detail#mv_trellis_settings_update)

Used to specify which settings to update.

------

### [mv_trellis_sidebar_content](../filters-detail#mv_trellis_sidebar_content)

HTML string for the sidebar. Used internally to apply lazy loading attributes to images.

------

### [mv_trellis_site_title_logo_alt_text](../filters-detail#mv_trellis_site_title_logo_alt_text)

Alt text used by the site logo. Defaults to the site name.

------

### [mv_trellis_site_title_logo_classes](../filters-detail#mv_trellis_site_title_logo_classes)

Class names to be added to site logo `<img>`tag.

------

### [mv_trellis_site_title_shortcode](../filters-detail#mv_trellis_site_title_shortcode)

Adjusts the HTML string for the site title displayed in the site footer. Defaults to the site name.

------

### [mv_trellis_site_title_text_classes](../filters-detail#mv_trellis_site_title_text_classes)

Adjusts classes for the site title markup.

------

### [mv_trellis_sw_ignore](../filters-detail#mv_trellis_sw_ignore)

Lists the paths to be ignored by the PWA service worker.

------

### [mv_trellis_the_title](../filters-detail#mv_trellis_the_title)

Adjusts the current page/post title.

------

### [mv_trellis_top_breadcrumbs_placement](../filters-detail#mv_trellis_top_breadcrumbs_placement)

Adjusts the hook targeted to output YOAST SEO breadcrumbs.

------

### [mv_trellis_web_stories_compatibility_styles](../filters-detail#mv_trellis_web_stories_compatibility_styles)

Adjusts the CSS styles applied to the Web Story archive pages.

------

### [mv_trellis_wordpress_link_shortcode](../filters-detail#mv_trellis_wordpress_link_shortcode)

Adjusts the HTML string for the link to WordPress in the site footer.
