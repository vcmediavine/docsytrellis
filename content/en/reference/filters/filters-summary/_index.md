---
tags: ["filters"]
title: "Filters Summary"
weight: 20
type: no_toc
description: >
  An alphabetically-sorted list of available filters in Trellis, showing only the filter name and description. Click on a filter name for detailed information.
---
### [mv_trellis_about_widget_image_height](../filters-detail#mv_trellis_about_widget_image_height)

Filters the height attribute to be set on the About Widget `<img>` tag.

------

### [mv_trellis_about_widget_image_width](../filters-detail#mv_trellis_about_widget_image_width)

Filters the width attribute to be set on the About Widget `<img>` tag.

------

### [mv_trellis_about_widget_image_size](../filters-detail#mv_trellis_about_widget_image_size)

Filters the size to be used when getting the About Widget image. This can be a Trellis image size, a WordPress image size, or a custom size.

------

### [mv_trellis_about_widget_image_sizes](../filters-detail#mv_trellis_about_widget_image_sizes)

Filters the sizes attribute value for the About Widget thumbnail.

------

### [mv_trellis_admin_runtime_dependencies](../filters-detail#mv_trellis_admin_runtime_dependencies)

Filters the dependencies needed for the mv-trellis/runtime script.

------

### [mv_trellis_allowed_google_fonts](../filters-detail#mv_trellis_allowed_google_fonts)

Filters the allowed Google Fonts list. Array keys are the labels provided to the settings and the values are the CSS values.

------

### [mv_trellis_allowed_non_google_fonts](../filters-detail#mv_trellis_allowed_non_google_fonts)

Filters the allowed Non-Google Fonts list. Array keys are the labels provided to the settings and the values are the CSS values.

------

### [mv_trellis_always_scan_template_files](../filters-detail#mv_trellis_always_scan_template_files)

Filters if the template part files should be scanned on each page load. When set to False, Trellis will only scan template part files upon activation, update, or when clearing the Trellis cache.

------

### [mv_trellis_article_nav_image_orientation](../filters-detail#mv_trellis_article_nav_image_orientation)

Filters the image orientation for post navigation images.

------

### [mv_trellis_article_nav_image_res](../filters-detail#mv_trellis_article_nav_image_res)

Filters the resolution to be used when getting the post navigation image size.

------

### [mv_trellis_async_styles_ignore](../filters-detail#mv_trellis_async_styles_ignore)

Filters the style filepaths that are ignored from loading asynchronously on the front-end.

------

### [mv_trellis_base_gutters](../filters-detail#mv_trellis_base_gutters)

Filters the base gutter sizes used for layout spacing. A value (in pixels) represents the amount of space to apply between layout elements. Uses the Layout Space value in Trellis Settings. Defaults to Comfortable.

------

### [mv_trellis_before_update_{$setting['slug']}](../filters-detail#mv_trellis_before_update_settingslug)

Filters a Trellis setting before updating it in the options table. This provides a way to trigger an action before the value is saved.

For example, when changing the featured image size, a developer might want to make sure all of the image sizes used in the srcset are generated.

------

### [mv_trellis_childtheme_link_shortcode](../filters-detail#mv_trellis_childtheme_link_shortcode)

Filters the output of the child theme link shortcode. In Trellis Settings, if the Hide Mediavine/Trellis Footer Links setting is disabled, Trellis will display a link to the child theme in the footer.

------

### [mv_trellis_comments_template](../filters-detail#mv_trellis_comments_template)

Filters the comments template filepath. Defaults to an empty string so that the comments.php file from the theme is loaded.

------

### [mv_trellis_copyright_shortcode](../filters-detail#mv_trellis_copyright_shortcode)

Filters the copyright shortcode output.

------

### [mv_trellis_crit_css_min_file_size](../filters-detail#mv_trellis_crit_css_min_file_size)

Filters the minimum size (in bytes) expected for a Critical CSS file to be saved. If the generated Critical CSS for a post or page is below this threshold, Trellis will not create a Critical CSS file.

------

### [mv_trellis_critical_css_rate_limit_in_seconds](../filters-detail#mv_trellis_critical_css_rate_limit_in_seconds)

Filters the rate limit (in seconds) between requests for generating Critical CSS.

------

### [mv_trellis_critical_css_timeout_in_seconds](../filters-detail#mv_trellis_critical_css_timeout_in_seconds)

Filters the amount of time (in seconds) before another Critical CSS request can be made. Prevents sites with errors from continuing to make requests that will timeout.

------

### [mv_trellis_css_allowlist](../filters-detail#mv_trellis_css_allowlist)

Filters a list of regex values to keep in the Non-Critical CSS file. Partial selector names can be passed in the array to designate multiple selectors.

------

### [mv_trellis_css_force_keep](../filters-detail#mv_trellis_css_force_keep)

Filters a list of regex values to include in the Critical CSS file. Regex patterns must match CSS selectors. Partial selector names can be passed in the array to designate multiple selectors.

------

### [mv_trellis_css_vars](../filters-detail#mv_trellis_css_vars)

Filters the CSS variables to be output in a page. Returns an array of CSS variables in `'name' => 'value'` format.

------

### [mv_trellis_default_featured_image_size](../filters-detail#mv_trellis_default_featured_image_size)

Filters the featured image size before it's returned. Defaults to the value of the Featured Image Size in Trellis Settings.

------

### [mv_trellis_disable_add_async_attribute](../filters-detail#mv_trellis_disable_add_async_attribute)

Filters whether to return early, disabling asynchronous loading on all enqueued scripts.

------

### [mv_trellis_disable_convert_iframe_to_lazyload_when_enabled](../filters-detail#mv_trellis_disable_convert_iframe_to_lazyload_when_enabled)

Filters whether to return early, preventing the addition of a `"loading=lazy"` attribute to iframes.

------

### [mv_trellis_disable_convert_image_to_lazyload_when_enabled](../filters-detail#mv_trellis_disable_convert_image_to_lazyload_when_enabled)

Filters whether to return early, disabling the adding or modifying of a `"loading=lazy"` attribute to images. 

------
### [mv_trellis_disable_eagerload_first_image](../filters-detail#mv_trellis_disable_eagerload_first_image)

Filters whether to return early, disabling eager loading on the first image in post content.

------

### [mv_trellis_disable_lazy_load_classes](../filters-detail#mv_trellis_disable_lazy_load_classes)

Filters an array of classes that are used to disable lazy loading for specific items.

------

### [mv_trellis_disable_ld_output_for_compatibility](../filters-detail#mv_trellis_disable_ld_output_for_compatibility)

Filters the addition of Trellis LD output for compatibility.

------

### [mv_trellis_disable_og_output_for_compatibility](../filters-detail#mv_trellis_disable_og_output_for_compatibility)

Filters the addition of Trellis Open Graph output for compatibility.

------

### [mv_trellis_disable_og_plugin_slugs](../filters-detail#mv_trellis_disable_og_plugin_slugs)

(Deprecated in 0.17.0) Filters an array of plugin slugs that will disable Trellis Open Graph output if any are active.

------

### [mv_trellis_disable_process_images](../filters-detail#mv_trellis_disable_process_images)

Filters whether to return early, disabling the processing of all images.

------

### [mv_trellis_disable_{$this->slug}_compatibility](../filters-detail#mv_trellis_disable_this-slug_compatibility)

Filters whether to return early, disabling all compatibility code for the specified plugin slug. Compatibility code is written by Mediavine and corresponds to plugins listed in Trellis’ compatibility directory (mediavine-trellis/inc/compatibility).

------

### [mv_trellis_disable_seo_output_for_compatibility](../filters-detail#mv_trellis_disable_seo_output_for_compatibility)

Filters the addition of Trellis SEO output.

------

### [mv_trellis_disable_set_image_cls_aspect_styles](../filters-detail#mv_trellis_disable_set_image_cls_aspect_styles)

Filters whether to return early, disabling the addition of inline aspect ratio styles.

------

### [mv_trellis_disable_set_image_data_pin_attribute](../filters-detail#mv_trellis_disable_set_image_data_pin_attribute)

Filters whether to return early, disabling the addition of the data-pin-media url.

------

### [mv_trellis_disable_set_image_dimensions](../filters-detail#mv_trellis_disable_set_image_dimensions)

Filters whether to return early, disabling the setting of image dimensions.

------

### [mv_trellis_disable_svg_preload_first_image](../filters-detail#mv_trellis_disable_set_image_dimensions)

Filters whether to return early, disabling the svg preload on the first image in post content.

------

### [mv_trellis_enable_lazy_load](../filters-detail#mv_trellis_enable_lazy_load)

Filters whether to return early, disabling Trellis lazy loading.

------

### [mv_trellis_enqueue_child_style](../filters-detail#mv_trellis_enqueue_child_style)

Filters whether the child style should be enqueued.

------

### [mv_trellis_enable_js_optimizations](../filters-detail#mv_trellis_enable_js_optimizations)

Filters whether JavaScript optimizations are enabled. This is used by compatibility classes for JavaScript optimization plugins.

------

### [mv_trellis_entry_content_classes](../filters-detail#mv_trellis_entry_content_classes)

Filters the classes added to the `.entry-content <div>`.

------

### [mv_trellis_excerpt_image_res](../filters-detail#mv_trellis_excerpt_image_res)

Filters the resolution to be used when getting the excerpt image size. Trellis includes the options of high, med_high, med, and low.

------

### [mv_trellis_excerpt_image_sizes](../filters-detail#mv_trellis_excerpt_image_sizes)

Filters the sizes attribute of the excerpt thumbnail images.

------

### [mv_trellis_featured_post_image_res](../filters-detail#mv_trellis_featured_post_image_res)

Filters the resolution to be used when getting the featured post thumbnail images. Trellis includes the options of high, med_high, med, and low.

------

### [mv_trellis_featured_post_image_sizes](../filters-detail#mv_trellis_featured_post_image_sizes)

Filters the featured post image sizes attribute.

------

### [mv_trellis_filter_{$post_type}_meta_fields](../filters-detail#mv_trellis_featured_post_image_sizes)

Filters the meta field blocks to be registered for this specific post type.

------

### [mv_trellis_filter_localized_font_types](../filters-detail#mv_trellis_filter_localized_font_types)

Filters which font types/formats are allowed to be localized.

------

### [mv_trellis_flags](../filters-detail#mv_trellis_flags)

Filters the Trellis flags to look for in the submitted URL.

------

### [mv_trellis_force_disable_critical_css](../filters-detail#mv_trellis_force_disable_critical_css)

Filters whether to stop a Critical CSS request.

------

### [mv_trellis_footer_copy_text](../filters-detail#mv_trellis_footer_copy_text)

Filters the footer copyright text before being processed by the `mv_trellis_copyright_shortcode` shortcode.

------

### [mv_trellis_get_{$post_type}_meta_fields](../filters-detail#mv_trellis_get_post_type_meta_fields)

Filters the meta fields for a specific post type.

------

### [mv_trellis_google_font_style_{$font_type}_default](../filters-detail#mv_trellis_google_font_style_font_type_default)

Filters the font styles for all fonts.

------

### [mv_trellis_google_font_style_{$font_type}_{$sanitized_font_name}](../filters-detail#mv_trellis_google_font_style_font_type_sanitized_font_name)

Filters the font styles for a specified font.

------

### [mv_trellis_grow_sidebar_compatibility_styles](../filters-detail#mv_trellis_grow_sidebar_compatibility_styles)

Filters style overrides for the Grow Social sidebar.

------

### [mv_trellis_grow_sidebar_margin_space](../filters-detail#mv_trellis_grow_sidebar_margin_space)

Filters the sidebar margin overrides for Grow Social. Helps to prevent Grow Social from covering content.

------

### [mv_trellis_grow_sidebar_media_query_max_width](../filters-detail#mv_trellis_grow_sidebar_media_query_max_width)

Filters the media query max width style override for Grow Social.

------

### [mv_trellis_grow_sidebar_media_query_min_width](../filters-detail#mv_trellis_grow_sidebar_media_query_min_width)

Filters the media query min width style override for Grow Social.

------

### [mv_trellis_hierarchy](../filters-detail#mv_trellis_hierarchy)

Filters the hierarchy of the file search order.

------

### [mv_trellis_image_orientation](../filters-detail#mv_trellis_image_orientation)

Filters the image orientation. This is the image size passed to `mv_trellis_get_attachment_image_tag`. Defaults to the value of the Featured Image Size in Trellis Settings.

------

### [mv_trellis_image_sizes](../filters-detail#mv_trellis_image_sizes)

Filters the list of theme image sizes before they are returned.

------

### [mv_trellis_image_sizes_attribute](../filters-detail#mv_trellis_image_sizes_attribute)

Filters the Trellis adjusted sizes attribute for an image.

------

### [mv_trellis_images_stop_process](../filters-detail#mv_trellis_images_stop_process)

(Only available if using Trellis Images) Filters whether to return early, disabling image processing.

------

### [mv_trellis_js_plugin_name](../filters-detail#mv_trellis_js_plugin_name)

Filters the displayed plugin name responsible for disabling JavaScript optimizations.

------

### [mv_trellis_license_required_settings](../filters-detail#mv_trellis_license_required_settings)

Filters the array of settings dependent on a Trellis license.

------

### [mv_trellis_link_shortcode](../filters-detail#mv_trellis_link_shortcode)

Filters the HTML string for the link to the Trellis homepage that appears in the site footer.

------

### [mv_trellis_local_script_model](../filters-detail#mv_trellis_local_script_model)

Filters the local model overrides for the Mediavine ad script wrapper.

------

### [mv_trellis_logo_sources](../filters-detail#mv_trellis_logo_sources)

Filters the `source` tags for the site logo that are output in a picture element.

------

### [mv_trellis_match_image_dimensions](../filters-detail#mv_trellis_match_image_dimensions)

Filters whether Trellis should check if specified dimensions match the registered image size.

------

### [mv_trellis_mediavine_link_shortcode](../filters-detail#mv_trellis_mediavine_link_shortcode)

Filters the HTML string for the link to the Mediavine homepage in the site footer.

------

### [mv_trellis_memory_exceeded](../filters-detail#mv_trellis_memory_exceeded)

Filters the result of Trellis' memory limit being reached.

------

### [mv_trellis_memory_limit_percent](../filters-detail#mv_trellis_memory_limit_percent)

Filters the percentage of available WordPress memory as a decimal. Trellis uses this amount to determine if there is enough memory available for its batch processes.

------

### [mv_trellis_model_sidebar_breakpoint](../filters-detail#mv_trellis_model_sidebar_breakpoint)

Filters the value added to the model for the sidebar breakpoint. This is used by the Mediavine ad script wrapper so that ads are not served when the sidebar is pushed below the content.

------

### [mv_trellis_nonasync_js_handles](../filters-detail#mv_trellis_nonasync_js_handles)

Filters the script handles that Trellis should not load asynchronously. Should match handles passed to `wp_register_script`.

------

### [mv_trellis_nonasync_js_urls](../filters-detail#mv_trellis_nonasync_js_urls)

Filters the list of script source URLs that Trellis should not load asynchronously.

------

### [mv_trellis_nonasync_js_prefixes](../filters-detail#mv_trellis_nonasync_js_prefixes)

Filters the list of handle prefixes where Trellis should not load scripts asynchronously. Prefixes should be at the start of the handles passed to `wp_register_script`.

------

### [mv_trellis_pages_pagination_args](../filters-detail#mv_trellis_pages_pagination_args)

Arguments to be passed to `the_posts_pagination`. Available arguments are described on the [WordPress paginate_links function page](https://developer.wordpress.org/reference/functions/paginate_links/).

------

### [mv_trellis_post_link_featured_image_sizes](../filters-detail#mv_trellis_post_link_featured_image_sizes)

Filters the post link featured image sizes attribute.

------

### [mv_trellis_process_content](../filters-detail#mv_trellis_process_content)

Filters the DOMDocument for making changes before it’s output to the browser.

------

### [mv_trellis_resolution_sizes](../filters-detail#mv_trellis_resolution_sizes)

Filters the resolution sizes to associate with image sizes.

------

### [mv_trellis_settings](../filters-detail#mv_trellis_settings)

Filters the theme settings. Used to add or modify theme settings whenever the settings are being built or rebuilt.

------

### [mv_trellis_settings_groups](../filters-detail#mv_trellis_settings_groups)

Filters the Trellis Settings tabs or groups.

------

### [mv_trellis_settings_update](../filters-detail#mv_trellis_settings_update)

Filters the theme settings to be updated.

------

### [mv_trellis_sidebar_content](../filters-detail#mv_trellis_sidebar_content)

Filters the sidebar HTML output. Used internally to apply lazy loading attributes to images.

------

### [mv_trellis_site_title_logo_alt_text](../filters-detail#mv_trellis_site_title_logo_alt_text)

Filters the site logo image alt text.

------

### [mv_trellis_site_title_logo_classes](../filters-detail#mv_trellis_site_title_logo_classes)

Filters the logo `<img>` tag classes.

------

### [mv_trellis_site_title_shortcode](../filters-detail#mv_trellis_site_title_shortcode)

Filters the site title shortcode output displayed in the site footer.

------

### [mv_trellis_site_title_text_classes](../filters-detail#mv_trellis_site_title_text_classes)

Filters the site title tag classes.

------

### [mv_trellis_skip_eagerload_classes](../filters-detail#mv_trellis_skip_eagerload_classes)

Filters a list of image classes that will not be eager loaded.

------

### [mv_trellis_sw_ignore](../filters-detail#mv_trellis_sw_ignore)

Filters the paths to be ignored by the service worker.

------

### [mv_trellis_the_title](../filters-detail#mv_trellis_the_title)

Filters the page title.

------

### [mv_trellis_top_breadcrumbs_placement](../filters-detail#mv_trellis_top_breadcrumbs_placement)

Filters the action hook called for the breadcrumb output near the top of pages.

------

### [mv_trellis_web_stories_compatibility_styles](../filters-detail#mv_trellis_web_stories_compatibility_styles)

Filters the Web Stories compatibility style overrides.

------

### [mv_trellis_wordpress_link_shortcode](../filters-detail#mv_trellis_wordpress_link_shortcode)

Filters the HTML string for the link to WordPress in the site footer.

------

### [mvt_processing_css_status_timeout](../filters-detail#mvt_processing_css_status_timeout)

Filters the expiration timestamp for when a Critical CSS request process should timeout.

------

### [mvt_requires_default_wp_fields](../filters-detail#mvt_requires_default_wp_fields)

Filters whether default WordPress Core comment fields should be used in the `comments_form` call in comments.php. If Trellis Comments are enabled, WordPress comment fields are not used.
