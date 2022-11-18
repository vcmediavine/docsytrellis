---
tags: ["filters"]
title: "Filters Detail"
linkTitle: "Filters Detail"
type: no_toc
weight: 30
description: >
  A detailed list of available filters in Trellis showing the filter name, description, syntax, default values, and arguments.
---

Trellis provides a number of filters that can be used to modify data or functionality in a child theme. You’ll find the filter’s name, description, syntax, default value, and any arguments it accepts in the list below.

{{% alert title="Note" %}}
While the syntax is shown using the `apply_filters()` function, these filters can also be used with `add_filter()`.
{{% /alert %}}

------

### mvt_processing_css_status_timeout

Sets the timeout period for the Processing state in Critical CSS.

```php
apply_filters( 'mvt_processing_css_status_timeout', int $value)
```

**Default**

- 7200 seconds (2 hours) from the current time.

**Arguments**

- $value `int` The amount of time measured in seconds since the Unix Epoch (January 1, 1970 00:00:00 GMT).

------

### mvt_requires_default_wp_fields

**Description**

Determines whether default WordPress comment fields should be used in the `comments_form` call in comments.php. If Trellis Comments are enabled, WordPress comment fields are not used.

```php
apply_filters('mvt_requires_default_wp_fields', bool $value)
```

**Default**

- False if Trellis Comments are enabled, True if Trellis Comments are disabled.

**Arguments**

- $value `bool` Whether to use default WordPress comment fields.

------

### mv_trellis_about_widget_image_height

Applied to the height attribute on the About Widget `<img>` tag.

```php
apply_filters('mv_trellis_about_widget_image_height', int $height)
```

**Default**

- 100

**Arguments**

- $height `int` The height of the About Widget image in pixels.

------

### mv_trellis_about_widget_image_width

Applied to the width attribute on the About Widget `<img>` tag.

```php
apply_filters( 'mv_trellis_about_widget_image_width', int $width)
```

**Default**

- 100

**Arguments**

- $width `int` The width of the About Widget image in pixels.

------

### mv_trellis_about_widget_image_size

The registered size to be used for the About Widget image. This can be a Trellis image size, a WordPress image size, or a custom size.

```php
apply_filters('mv_trellis_about_widget_image_size', string $img_size)
```

**Default**

- mv_trellis_1x1_low_res

**Arguments**

- $img_size `string` The registered image size.

------

### mv_trellis_about_widget_image_sizes

Applied to the sizes attribute value for the About Widget thumbnail.

```php
apply_filters('mv_trellis_about_widget_image_sizes', string $sizes)
```

**Default**

- 100px

**Arguments**

- $sizes `string` The value of the About Widget thumbnail sizes attribute.

------

### mv_trellis_admin_runtime_dependencies

Lists the registered dependencies needed for the mv-trellis/runtime script.

```php
apply_filters('mv_trellis_admin_runtime_dependencies', array $list)
```

**Default**

- Empty array

**Arguments**

- $list `array` A list of registered dependencies.

------

### mv_trellis_allowed_google_fonts

Returns a list of allowed Google Fonts to be supplied to Body Font and Heading Font settings. Array keys are the labels provided to the settings and the values are the CSS values.

```php
apply_filters('mv_trellis_allowed_google_fonts', array $list)
```

**Default**

```php
'Abril Fatface'     => '"Abril Fatface",serif',
'Amatic SC'         => '"Amatic SC",cursive,serif',
'Crimson Text'      => '"Crimson Text",serif',
'Great Vibes'       => '"Great Vibes",cursive,serif',
'Inconsolata'       => 'Inconsolata,monospace',
'Libre Baskerville' => '"Libre Baskerville",serif',
'Lato'              => 'Lato,sans-serif',
'Lora'              => 'Lora,serif',
'Merriweather'      => 'Merriweather,serif',
'Mr De Haviland'    => '"Mr De Haviland",cursive,serif',
'Noto Serif'        => '"Noto Serif",serif',
'Open Sans'         => '"Open Sans",sans-serif',
'Poppins'           => 'Poppins,sans-serif',
'Playball'          => '"Playball",fantasy,serif',
'Playfair Display'  => '"Playfair Display",serif',
'Raleway'           => 'Raleway,sans-serif',
'Roboto Slab'       => '"Roboto Slab",serif',
'Tangerine'         => 'Tangerine,cursive,serif',
'Work Sans'         => '"Work Sans",sans-serif',
```

**Arguments**

- $list `array` Key/value list of allowed Google Fonts.

------

### mv_trellis_allowed_non_google_fonts

Returns a list of web safe fonts to be supplied to Body Font and Heading Font settings. Array keys are the labels provided to the settings and the values are the CSS values.

```php
apply_filters('mv_trellis_allowed_non_google_fonts', array $list)
```

**Default**

```php
'Arial (Web Safe)'           => 'Arial,"Helvetica Neue",Helvetica,sans-serif',
'Baskerville (Web Safe)'     => 'Baskerville,"Baskerville Old Face","Hoefler Text",Garamond,"Times New Roman",serif',
'Book Antiqua (Web Safe)'    => '"Book Antiqua",Palatino,"Palatino Linotype","Palatino LT STD",Georgia,serif',
'Calibri (Web Safe)'         => 'Calibri,Candara,Segoe,"Segoe UI",Optima,Arial,sans-serif',
'Cambria (Web Safe)'         => 'Cambria,Georgia,serif',
'Century Gothic (Web Safe)'  => '"Century Gothic",CenturyGothic,AppleGothic,sans-serif',
'Constantia (Web Safe)'      => 'Constantia,"Lucida Bright",Lucidabright,"Lucida Serif",Lucida,"DejaVu Serif","Bitstream Vera Serif","Liberation Serif",Georgia,serif',
'Courier New (Web Safe)'     => '"Courier New",Courier,"Lucida Sans Typewriter","Lucida Typewriter",monospace',
'Franklin Gothic (Web Safe)' => '"Franklin Gothic Medium","Franklin Gothic","ITC Franklin Gothic",Arial,sans-serif',
'Futura (Web Safe)'          => 'Futura,"Trebuchet MS",Arial,sans-serif',
'Garamond (Web Safe)'        => 'Garamond,Baskerville,"Baskerville Old Face","Hoefler Text","Times New Roman",serif',
'Georgia (Web Safe)'         => 'Georgia,Times,"Times New Roman",serif',
'Gill Sans (Web Safe)'       => '"Gill Sans","Gill Sans MT",Calibri,sans-serif',
'Lucida Bright (Web Safe)'   => '"Lucida Bright",Georgia,serif',
'Palatino (Web Safe)'        => 'Palatino,"Palatino Linotype","Palatino LT STD","Book Antiqua",Georgia,serif',
'System Default (Web Safe)'  => 'system,-apple-system,".SFNSText-Regular","San Francisco","Roboto","Segoe UI","Helvetica Neue","Lucida Grande",sans-serif',
'Tahoma (Web Safe)'          => 'Tahoma,Verdana,Segoe,sans-serif',
'Times New Roman (Web Safe)' => 'TimesNewRoman,"Times New Roman",Times,Baskerville,Georgia,serif',
'Trebuchet (Web Safe)'       => '"Trebuchet MS","Lucida Grande","Lucida Sans Unicode","Lucida Sans",Tahoma,sans-serif',
'Verdana (Web Safe)'         => 'Verdana,Geneva,sans-serif',
```

**Arguments**

- $list `array` Key/value list of allowed Non-Google fonts.

------

### mv_trellis_always_scan_template_files

Determines if the Trellis template part files should be scanned on every page load. When set to False, Trellis will only scan template part files upon activation, update, or when clearing the Trellis cache.

```php
apply_filters( 'mv_trellis_always_scan_template_files', bool $value )
```

**Default**

- False

**Arguments**

- $value `bool` Whether to scan on every page load.

------

### mv_trellis_article_nav_image_orientation

Applies the image orientation for post navigation images.

```php
apply_filters( 'mv_trellis_article_nav_image_orientation', string $orientation )
```

**Default**

- mv_trellis_4x3

**Arguments**

- $orientation `string` The image orientation as set by the Featured Image Size setting in the Mediavine Trellis Dashboard. Default options include mv_trellis_1x1, mv_trellis_3x4, mv_trellis_4x3, mv_trellis_16x9, and full.

------

### mv_trellis_article_nav_image_res

Applies the resolution to be used for the post navigation image size.

```php
apply_filters( 'mv_trellis_article_nav_image_res', string $value )
```

**Default**

- low

**Arguments**

- $value `string` The image resolution to use for the post navigation size. Default options include high, med_high, med, and low.

------

### mv_trellis_async_styles_ignore

A list of filepaths to ignore from asynchronous stylesheet loading on the site’s front-end.

```php
apply_filters( 'mv_trellis_async_styles_ignore', array $list )
```

**Default**

- Empty array

**Arguments**

- $list `array` List of filepaths to ignore.

------

### mv_trellis_base_gutters

Applies to the base gutter sizes used for layout spacing. A value (in pixels) represents the amount of space to apply between layout elements. Uses the Layout Space setting in the Mediavine Trellis Dashboard. Defaults to Comfortable. These values impact the base padding and margin values used by Trellis CSS variables:

- gutter-small = base/2
- gutter = base
- gutter-double = base * 2
- gutter-large = base * 2.5

The return value should match one of the specified keys.

```php
apply_filters( 'mv_trellis_base_gutters', array $base_gutters )
```

**Default**

- [ 'Compact' => 10, 'Comfortable' => 20 ]

**Arguments**

- $base_gutters `array` The base values for Compact and Comfortable spacing.

------

### mv_trellis_before_update_{$setting[’slug’]}

Filters a Trellis setting before updating it in the options table. This provides a way to trigger an action before the value is saved.

For example, when changing the featured image size, a developer might want to make sure all of the image sizes used in the srcset are generated.

```php
apply_filters( 'mv_trellis_before_update_' . $setting['slug'], array $setting )
```

**Default**

- Array of all the Trellis setting data.

**Arguments**

- $setting `array` The specified setting data.

------

### mv_trellis_childtheme_link_shortcode

Applies the HTML string for the link to the child theme. If the Hide Footer Links setting is off, Trellis will display a link to the child theme in the footer.

```php
apply_filters( 'mv_trellis_childtheme_link_shortcode', string $output, array $atts )
```

**Default**

- The HTML link to the Trellis Framework, currently [https://mediavine.com/](https://mediavine.com/').

**Arguments**

- $output `string` HTML output of the shortcode.
- $atts `array` List of shortcode attributes.

------

### mv_trellis_comments_template

The path to the comments template file. Defaults to an empty string so that the comments.php file from the theme is loaded.

```php
apply_filters( 'mv_trellis_comments_template', string $comments_template_file );
```

**Default**

- Empty

**Arguments**

- $comments_template_file `string` The location of the comments template file.

------

### mv_trellis_copyright_shortcode

HTML string for the copyright information shown in the footer.

```php
apply_filters( 'mv_trellis_copyright_shortcode', string $output, array $atts )
```

**Default**

- Copyright © {current_year} {site_title}

**Arguments**

- $output `string` HTML copyright output of the shortcode.
- $atts `array` List of shortcode attributes.

------

### mv_trellis_crit_css_min_file_size

Specifies the minimum size (in bytes) required to save a Critical CSS file. If the generated Critical CSS for a post or page is below this threshold, Trellis will not create a Critical CSS file.

```php
apply_filters('mv_trellis_crit_css_min_file_size', int $min_crit_css_size	)
```

**Default**

- 2048

**Arguments**

- $min_crit_css_size `int` Minimum size in bytes.

------

### mv_trellis_critical_css_rate_limit_in_seconds

Applies the rate (in seconds) of calls to the Trellis Critical CSS API when generating critical CSS files.

```php
apply_filters( 'mv_trellis_critical_css_rate_limit_in_seconds', int|bool $critical_css_rate_limit_in_seconds );
```

**Default**

- 30

**Arguments**

- $critical_css_rate_limit_in_seconds `int|bool` Rate limit in seconds. Set to False to disable critical CSS rate limiting.

------

### mv_trellis_critical_css_timeout_in_seconds

Applies the Critical CSS request timeout duration. After this time, if a request has not been answered, it will timeout.

```php
apply_filters( 'mv_trellis_critical_css_timeout_in_seconds', int|bool $value )
```

**Default**

- 172800 ( two days)

**Arguments**

- $critical_css_timeout_in_seconds `int|bool` Timeout duration in seconds. Set to False to allow Critical CSS requests indefinitely.

------

### mv_trellis_css_allowlist

Applies a list of CSS selectors that will be kept in the Non-Critical CSS file. Partial selector names can be passed in the array to designate multiple selectors.

```php
apply_filters( 'mv_trellis_css_allowlist', array $bypass_settings )
```

**Default**

- Empty array

**Arguments**

- $bypass_settings `array` List of CSS selectors that will be kept in the secondary Non-Critical CSS file.

------

### mv_trellis_css_force_keep

Applies a list of CSS selectors to be kept in the Critical CSS file. Partial selector names can be passed in the array to designate multiple selectors.

```php
apply_filters( 'mv_trellis_css_force_keep', array $force_keep_settings );
```

**Default**

- Empty array

**Arguments**

- $force_keep_settings `array` List of CSS selectors to be kept in the primary Critical CSS file.

------

### mv_trellis_css_vars

Applies the available CSS variables for styling. Returns an array of CSS variables in ‘name’ => 'value' format.

```php
apply_filters( 'mv_trellis_css_vars', array $css_vars, array $css_options )
```

**Default**

Variable values are those set in the Mediavine Trellis Dashboard.

```php
'color-body'       => $css_options['color_body'],
'color-link'       => $css_options['color_link'],
'color-link-hover' => $css_options['color_link_hover'],
'font-body'        => $css_options['google_font_body'],
'font-heading'     => $css_options['google_font_heading'],
'font-size-ex-sm'  => $base_font_fl * 0.667 . 'rem',
'font-size-sm'     => $base_font_fl * 0.875 . 'rem',
'font-size'        => $css_options['font_size'],
'font-size-lg'     => $base_font_fl * 1.125 . 'rem',
'color-primary'    => '#' . str_replace( '#', '', $primary_color ),
'color-link'       => 'var(--mv-trellis-color-primary)',
'color-secondary'  => '#' . str_replace( '#', '', $secondary_color ),
'color-link-hover' => 'var(--mv-trellis-color-secondary)',
'max-logo-size'    => $max_logo_size;
```

**Arguments**

- $css_vars `array` List of CSS variables in 'name' => 'value' format.
- $css_options `array` CSS variable options set in the theme's functions.

------

### mv_trellis_default_featured_image_size

Applies the slug of the image size to be used as the featured image size. Defaults to the value of the Featured Image Size setting in the Mediavine Trellis Dashboard.

```php
apply_filters( 'mv_trellis_default_featured_image_size', array $default )
```

**Default**

- mv_trellis_4x3

**Arguments**

- $default `array` The default image size to use, including optional resolution sizes.

------

### mv_trellis_disable_add_async_attribute

Disables asynchronous loading on all enqueued scripts.

```php
apply_filters( 'mv_trellis_disable_add_async_attribute', bool $value )
```

**Default**

- False

**Arguments**

- $value `bool` Whether to disable asynchronous loading of scripts.

------

### mv_trellis_disable_convert_iframe_to_lazyload_when_enabled

Disables adding “loading=lazy” attribute to iframes.

```php
apply_filters( 'mv_trellis_disable_convert_iframe_to_lazyload_when_enabled', bool $value )
```

**Default**

- False

**Arguments**

- $value `bool` Whether to disable adding “loading=lazy” attribute to iframes.

------

### mv_trellis_disable_convert_image_to_lazyload_when_enabled

Disables adding “loading=lazy” attribute to images. 

```php
apply_filters( 'mv_trellis_disable_convert_image_to_lazyload_when_enabled', bool $value )
```

**Default**

- False

**Arguments**

- $value `bool` Whether to disable adding “loading=lazy” attribute to images.

------

### mv_trellis_disable_lazy_load_classes

An array of class names on image tags that will disable lazy loading for an image.

```php
apply_filters( 'mv_trellis_disable_lazy_load_classes', array $values )
```

**Default**

- ['no-lazyload']

**Arguments**

- $values `array` List of classes that will not be lazy loaded.

------

### mv_trellis_disable_og_plugin_slugs

An array of plugin slugs that will disable Trellis Open Graph output if any are active.

```php
apply_filters( 'mv_trellis_disable_og_plugin_slugs', array $disable_og_plugin_slugs )
```

**Default**

- ['wordpress-seo’]

**Arguments**

- $disable_og_plugin_slugs `array` A list of plugin slugs that disable Trellis Open Graph output.

------

### mv_trellis_disable_process_images

Disables processing of all image optimizations.

```php
apply_filters( 'mv_trellis_disable_process_images', bool $value )
```

**Default**

- False

**Arguments**

- $value `bool` Whether to disable image processing on all images.

------

### mv_trellis_disable_{$this->slug}_compatibility

Disables compatibility code for the specified plugin slug. Compatibility code is written by Mediavine and corresponds to plugins listed in Trellis’ compatibility directory (mediavine-trellis/inc/compatibility).

```php
apply_filters( "mv_trellis_disable_{$this->slug}_compatibility", bool $value )
```

**Default**

- False

**Arguments**

- $value `bool` Whether to disable compatibility code for the specified plugin slug.

------

### mv_trellis_disable_set_image_cls_aspect_styles

Disables adding inline aspect ratio styles.

```php
apply_filters( 'mv_trellis_disable_set_image_cls_aspect_styles', bool $value )
```

**Default**

- False

**Arguments**

- $value `bool` Whether to disable adding inline aspect ratio styles.

------

### mv_trellis_disable_set_image_data_pin_attribute

Disables adding data-pin-media attribute to images. Allows specifying an alternate version of an image for Pinterest.

```php
apply_filters( 'mv_trellis_disable_set_image_data_pin_attribute', bool $value )
```

**Default**

- False

Arguments

- $value `bool` Whether to disable adding data-pin-media attribute.

------

### mv_trellis_disable_set_image_dimensions

Disables setting image width and height attributes on all images.

```php
apply_filters( 'mv_trellis_disable_set_image_dimensions', bool $value )
```

**Default**

- False

**Arguments**

- $value `bool` Whether to disable setting image dimension attributes.

------

### mv_trellis_enable_lazy_load

Determines whether lazy loading is enabled for images and iframes.

<aside>
✏️ **Note:** Mediavine recommends keeping lazy loading on for the best performance.

</aside>

```php
apply_filters( 'mv_trellis_enable_lazy_load', bool $value )
```

**Default**

- True

**Arguments**

- $value `bool` Whether lazy loading is enabled or disabled.

------

### mv_trellis_enqueue_child_style

Determines whether the child theme style should be enqueued.

```php
apply_filters( 'mv_trellis_enqueue_child_style', bool $value )
```

**Default**

- True

**Arguments**

- $value `bool` Whether the child style is enqueued or not.

------

### mv_trellis_enable_js_optimizations

Determines if JavaScript optimizations are enabled. This is used by compatibility classes for JavaScript optimization plugins. Defaults to True but will read the value of the Trellis setting in the Mediavine Trellis Dashboard.

```php
apply_filters( 'mv_trellis_enable_js_optimizations', bool $value )
```

**Default**

- True

**Arguments**

- $value `bool` Whether JavaScript optimizations should be enabled.

------

### mv_trellis_entry_content_classes

List of CSS classes added to the entry-content `<div>`.

```php
apply_filters( 'mv_trellis_entry_content_classes', array $class )
```

**Default**

- Empty array

**Arguments**

- $class `array` List of classes added to entry-content.

------

### mv_trellis_excerpt_image_res

The resolution to be applied when getting the excerpt image size. Trellis includes the options of high, med_high, med, and low.

```php
apply_filters( 'mv_trellis_excerpt_image_res', string $image_res )
```

**Default**

- low

**Arguments**

- $image_res `string` The image resolution.

------

### mv_trellis_excerpt_image_sizes

Applies the sizes attribute to excerpt thumbnail images.

```php
apply_filters( 'mv_trellis_excerpt_image_sizes', string $sizes )
```

**Default**

- (max-width: 599px) 300px, 270px

**Arguments**

- $sizes `string` The sizes attribute value of excerpt thumbnail images.

------

### mv_trellis_featured_post_image_res

The resolution to be used when getting the featured post thumbnail image. Trellis includes the options of high, med_high, med, and low.

```php
$image_res = apply_filters( 'mv_trellis_featured_post_image_res', string $image_res );
```

**Default**

- med

**Arguments**

- $image_res `string` The featured post thumbnail image resolution.

------

### mv_trellis_featured_post_image_sizes

The featured post image sizes attribute.

```php
apply_filters( 'mv_trellis_featured_post_image_sizes', string $sizes )
```

**Default**

- (max-width: 340px) calc(100vw - 40px), (max-width: 450px) calc(100vw - 100px), (max-width: 959px) 350px, (max-width: 1134px) 275px, 350px

**Arguments**

- $sizes `string` The value of the sizes attribute for featured post images.

------

### mv_trellis_filter_localized_font_types

Specifies which font types/formats are allowed to be localized.

```php
apply_filters( 'mv_trellis_filter_localized_font_types', array $font_types )
```

**Default**

- [ 'woff2']

**Arguments**

- $font_types `array` List of types/formats of fonts to localize.

------

### mv_trellis_flags

An array of flags that Trellis will look for in the submitted URL. Uses the `mvt_flags` query parameter.

```php
apply_filters( 'mv_trellis_flags', array $flags )
```

**Default**

- Empty array

**Arguments**

- $flags `array` List of Trellis URL flags.

------

### mv_trellis_force_disable_critical_css

Stops Critical CSS requests.

```php
apply_filters( 'mv_trellis_force_disable_critical_css', bool $value )
```

**Default**

- False

**Arguments**

- $value `bool` Whether to disable Critical CSS processing.

------

### mv_trellis_footer_copy_text

Sets the footer copyright text before being passed to `mv_trellis_copyright_shortcode`.

```php
apply_filters( 'mv_trellis_footer_copy_text', string $copy_text )
```

**Default**

- Copyright and footer links text.

**Arguments**

- $copy_text `string` Contents of the copyright text.

------

### mv_trellis_get_{$post_type}_meta_fields

Applies the Trellis meta fields for a specific post type.

```php
apply_filters( 'mv_trellis_get_' . string $post_type . '_meta_fields', array $fields )
```

**Default**

- Empty array

**Arguments**

- $fields `array` Trellis-specific meta fields and their attributes.

------

### mv_trellis_google_font_style_{$font_type}_default

Applies the default font styles to use for a particular type of Google Font.

```php
apply_filters( "mv_trellis_google_font_style_{$font_type}_default", array $google_font_style )
```

**Default**

- [ '400', '400i', '700', '700i' ]

**Arguments**

- $google_font_style `array` A list of styles to load.

------

### mv_trellis_google_font_style_{$font_type}_{$sanitized_font_name}

Applies the font styles for a specific Google font.

```php
apply_filters( "mv_trellis_google_font_style_{$font_type}_{$sanitized_font_name}", array $google_font_style )
```

**Default**

- [ '400', '400i', '700', '700i' ]

**Arguments**

- $google_font_style `array` A list of styles to load for a particular font.

------

### mv_trellis_grow_sidebar_compatibility_styles

Used to add to or replace custom styles for Grow Social when the plugin is active.

```php
apply_filters( 'mv_trellis_grow_sidebar_compatibility_styles', string $grow_sidebar_styles )
```

**Default**

```css
@media only screen and (min-width: ' . $media_query_min_width . ') and (max-width: ' . $media_query_max_width . ')
{
    .has-grow-sidebar .content > .wrapper,.has-grow-sidebar .footer > .wrapper
    {' . $sidebar_margin_css . '}
    .has-grow-sidebar .wrapper-content
      {padding-left:10px;padding-right:10px;}
}
@media only screen and (max-width:1184px)
{
    .has-grow-sidebar .widget-container.mv_trellis_mobile_hide{display:none;}
    .has-grow-sidebar .wrapper-content{display:block;}
}
```

**Arguments**

- $grow_sidebar_styles `string` CSS styles to adjust the display of the Grow Social floating sidebar when it’s active.

------

### mv_trellis_grow_sidebar_margin_space

Adjusts the sidebar margin space for the Grow Social sticky sidebar when the plugin is active. Helps to prevent Grow Social from covering content.

```php
apply_filters( 'mv_trellis_grow_sidebar_margin_space', string $value )
```

**Default**

- 60px

**Arguments**

- $value `string` The margin to be used (in pixels).

------

### mv_trellis_grow_sidebar_media_query_min_width

Allows child themes to adjust the minimum viewport width for when the Grow Social styles are active.

```php
apply_filters( 'mv_trellis_grow_sidebar_media_query_min_width', string $value )
```

**Default**

- 721px

**Arguments**

- $value `string` Specifies the min width that these styles are applied.

------

### mv_trellis_grow_sidebar_media_query_max_width

Allows child themes to adjust the maximum viewport width for when the Grow Social styles are active.

```php
apply_filters( 'mv_trellis_grow_sidebar_media_query_max_width', string $value )
```

**Default**

- 1350px

Arguments

- $value `string` Specifies the max width that these styles are applied.

------

### mv_trellis_hierarchy

The array of file names to use when searching for template parts, in hierarchy of search order.

**Default**

<aside>
✏️ **Note:** This list shows the default name and order of template parts to search in plain text, but an array must be passed as an argument to the filter.

</aside>

```
1. {$slug}-front-page-{$theme_style}.php
2. {$slug}-front-page.php
3. {$slug}-home-{$theme_style}.php
4. {$slug}-home.php
5. {$slug}-author-{$theme_style}.php
6. {$slug}-author.php
7. {$slug}-category-{$theme_style}.php
8. {$slug}-category.php
9. {$slug}-archive-{$post_type}-{$theme_style}.php
10. {$slug}-archive-{$post_type}.php
11. {$slug}-taxonomy-{$theme_style}.php
12. {$slug}-taxonomy.php
13. {$slug}-date-{$theme_style}.php
14. {$slug}-date.php
15. {$slug}-tag-{$theme_style}.php
16. {$slug}-tag.php
17. {$slug}-archive-{$theme_style}.php
18. {$slug}-archive.php
19. {$slug}-{$post_type}-{$theme_style}.php
20. {$slug}-{$post_type}.php
21. {$slug}-singular-{$theme_style}.php
22. {$slug}-singular.php
23. {$slug}-search-{$theme_style}.php
24. {$slug}-search.php
25. {$slug}-404-{$theme_style}.php
26. {$slug}-404.php
27. {$slug}-{$theme_style}.php
28. {$slug}.php
```

**Arguments**

- $parts_to_search `array` List of template parts in the file search order.

------

### mv_trellis_image_orientation

Specifies the article nav image orientation. This is the image size passed to `mv_trellis_get_attachment_image_tag`. Defaults to the value of the Featured Image Size setting in the Mediavine Trellis Dashboard.

```php
apply_filters( 'mv_trellis_image_orientation', string $orientation )
```

**Default**

- mv_trellis_4x3

**Arguments**

- $orientation `string` The slug of the image orientation.

------

### mv_trellis_image_sizes

A list of theme images sizes in a key/value format. These options are passed to the Featured Image Size setting in the Mediavine Trelllis Dashboard. The array should contain a label key with the value shown in the user interface, and a value key with the slug.

```php
apply_filters( 'mv_trellis_image_sizes', array $options )
```

**Default**

- Array of Trellis custom image sizes in `slug => name` format.

**Arguments**

- $options `array` Theme image sizes in a key/value format.

------

### mv_trellis_image_sizes_attribute

Adjusts the Trellis sizes attribute for an image.

```php
apply_filters( 'mv_trellis_image_sizes_attribute', string $sizes, string|array $size, string|null $image_src, array|null $image_meta, int $attachment_id )
```

**Default**

- (max-width: 760px) calc(100vw - ' . $css_gutter_double . '), 720px

**Arguments**

- $sizes `string` A source size value for use in a sizes attribute.
- $size `string|array` The requested image size. It can be any registered image size name or an array of width and height values in pixels (in that order).
- $image_src `string|null` The URL to the image file or null.
- $image_meta `array|null` The image metadata as returned by `wp_get_attachment_metadata` or null.
- $attachment_id `int` The image attachment ID of the original image or 0. If set to 0, only  $image_meta is used.

------

### mv_trellis_js_plugin_name

Displays the plugin name responsible for disabling JavaScript optimizations.

```php
apply_filters( 'mv_trellis_js_plugin_name', string $value )
```

**Default**

- Empty

**Arguments**

- $value `string` The plugin name.

------

### mv_trellis_license_required_settings

An array of settings dependent on a Trellis license.

```php
apply_filters( 'mv_trellis_license_required_settings', array $license_dependent )
```

**Default**

```php
$license_dependent = [
        'google_font_body',
        'google_font_heading',
        'featured_image_size',
        'google_analytics_delay',
        'hide_footer_links',
        'enable_pwa',
        'site_logo',
        'primary_css_color',
        'secondary_css_color',
        'background_accent_css_color',
        'max_logo_size',
        'el_comfort_level',
        'pwa_short_name',
        'pwa_theme_color',
        'site_icon',
        'js_optimizations',
      ];
```

**Arguments**

- $license_dependent `array` List of slugs for settings that are dependent on a license.

------

### mv_trellis_link_shortcode

HTML string for the link to the Trellis homepage that appears in the site footer.

```php
apply_filters( 'mv_trellis_link_shortcode', string $output, array $atts )
```

**Default**

```html
<a href="https://mediavine.com/" target="_blank" rel="noopener nofollow">Trellis Framework</a>
```

**Arguments**

- $output `string` HTML Trellis link output.
- $atts `array` Trellis link shortcode attributes.

------

### mv_trellis_local_script_model

Allows overriding of the Mediavine Control Panel (MCP) ad settings for the script wrapper.

```php
apply_filters( 'mv_trellis_local_script_model', array $local_model_default_values )
```

**Default**

```php
$local_model_default_values = [
        'optimize_mobile_pagespeed'  => true,
        'optimize_desktop_pagespeed' => true,
        'content_selector'           => '.mvt-content',
        'footer_selector'            => 'footer.footer',
        'content_selector_mobile'    => '.mvt-content',
        'comments_selector'          => '',
        'sidebar_atf_selector'       => '.sidebar-primary .widget-container:nth-last-child(3)',
        'sidebar_atf_position'       => 'afterend',
        'sidebar_btf_selector'       => '.mv-sticky-slot',
        'sidebar_btf_position'       => 'beforeend',
        'content_stop_selector'      => '',
        'sidebar_btf_stop_selector'  => 'footer.footer',
        'custom_css'                 => '',
        'ad_box'                     => true,
        /**
         * Filters the value added to the model for the sidebar breakpoint. Default is 1135.
         * (Advanced use)
         *
         * @param string The last pixel width that the sidebar is viewable
         */
        'sidebar_minimum_width'      => apply_filters( 'mv_trellis_model_sidebar_breakpoint', '1135' ),
      ];
```

**Arguments**

- $local_model_values `array` Key/value pairs to override.

------

### mv_trellis_logo_sources

Allows Trellis Images to offer an optimized image version via source tags.

```php
apply_filters( 'mv_trellis_logo_sources', '', array $img_html )
```

**Default**

```php
$img_html = mv_trellis_get_attachment_image_tag(
      $logo_id,
      'full',
      [
        'class'          => $image_classes,
        'alt'            => $alt_text,
        'data-pin-nopin' => 'true',
      ],
      null,
      false
    );
```

**Arguments**

- $img_html `array` Arguments for getting logo sources.

------

### mv_trellis_match_image_dimensions

Determines if Trellis should check that dimensions match the registered image size.

```php
apply_filters( 'mv_trellis_match_image_dimensions', bool $value, int $img_id, string $img_size )
```

**Default**

- False

**Arguments**

- $value `bool` Whether the image dimensions should match.
- $img_id `int` The ID of the image.
- $img_size `string` The size of the image.

------

### mv_trellis_mediavine_link_shortcode

HTML string for the link to the Mediavine homepage in the site footer.

```php
apply_filters( 'mv_trellis_mediavine_link_shortcode', string $output, array $atts )
```

**Default**

```html
<a href="https://www.mediavine.com/" target="_blank" rel="noopener nofollow">Mediavine</a>
```

**Arguments**

- $output `string` Mediavine link output.
- $atts `array` Mediavine link shortcode attributes.

------

### mv_trellis_memory_exceeded

Returns whether Trellis has exceeded its memory limit. Returns False if the memory limit has not been reached. Memory limit is set via `mv_trellis_memory_limit_percent`.

```php
apply_filters( 'mv_trellis_memory_exceeded', bool $return )
```

**Default**

- False

**Arguments**

- $return `bool` Whether Trellis has exceeded its memory limit.

------

### mv_trellis_memory_limit_percent

Sets the percentage of available WordPress memory as a decimal. Trellis uses this amount to determine if there is enough memory available for its batch processes.

```php
apply_filters( 'mv_trellis_memory_limit_percent', float $value )
```

**Default**

- 0.9

**Arguments**

- $percent_of_memory `float` The percentage of available WordPress memory Trellis can use.

------

### mv_trellis_model_sidebar_breakpoint

Adjusts the value added for the sidebar breakpoint. This is used by the Mediavine ad script wrapper so that ads are not served when the sidebar is pushed below the content.

```php
apply_filters( 'mv_trellis_model_sidebar_breakpoint', string $value )
```

**Default**

- 1135

**Arguments**

- $value `string` The last pixel width that the sidebar is viewable.

------

### mv_trellis_nonasync_js_handles

List of handles where Trellis should not load scripts asynchronously. Should match handles passed to `wp_register_script`.

```php
apply_filters( 'mv_trellis_nonasync_js_handles', array $disallowed_handles )
```

**Default**

- Empty array

**Arguments**

- $disallowed_handles `array` List of handles to be compared against.

------

### mv_trellis_nonasync_js_urls

List of script source URLs that Trellis should not load asynchronously.

```php
apply_filters( 'mv_trellis_nonasync_js_urls', array $disallowed_urls)
```

**Default**

- Empty array

**Arguments**

- $disallowed_urls `array` List of URLs to be compared against.

------

### mv_trellis_nonasync_js_prefixes

List of handle prefixes where Trellis should not load scripts asynchronously. Prefixes should be at the start of the handles passed to `wp_register_script`.

```php
apply_filters( 'mv_trellis_nonasync_js_prefixes', $disallowed_prefixes )
```

**Default**

- Empty array

**Arguments**

- $disallowed_prefixes `array` List of handle prefixes to be compared against.

------

### mv_trellis_pages_pagination_args

Arguments to be passed to `the_posts_pagination`. Available arguments are described on the [WordPress paginate_links function page](https://developer.wordpress.org/reference/functions/paginate_links/)**.**

```php
apply_filters( 'mv_trellis_pages_pagination_args', array $posts_pagination_args )
```

**Default**

- Empty array

**Arguments**

- $posts_pagination_args `array` Arguments for displaying pagination links.

------

### mv_trellis_post_link_featured_image_sizes

Outputs the sizes attribute in featured image post links.

```php
apply_filters( 'mv_trellis_post_link_featured_image_sizes', string $sizes )
```

**Default**

- (max-width: 599px) 320px, (max-width: 700px) calc(50vw - 30px), 320px

**Arguments**

- $sizes `string` Contents of the sizes attribute for featured images in post links.

------

### mv_trellis_process_content

Returns the DOM document to make changes before it’s output to the browser.

```php
apply_filters( 'mv_trellis_process_content', \DOMDocument $content_dom )
```

**Default**

- DOMDocument of the content being processed (the_content or primary sidebar).

**Arguments**

- $content_dom `\DOMDocument` The DOMDocument content.

------

### mv_trellis_resolution_sizes

List of resolution sizes to associate with image sizes.

```php
apply_filters( 'mv_trellis_resolution_sizes',  array $resolution_sizes, array $custom_image_sizes )
```

**Default**

- [ 'high', 'med_high', 'med', 'low' ]

**Arguments**

- $resolution_sizes `array` List of allowed resolution sizes.
- $custom_image_sizes `array` Custom image sizes to be added through the theme.

------

### mv_trellis_settings

Used to add or modify theme settings whenever the settings are being built or rebuilt. A Flags key can be used to force a value update to the default.

For example, 'flags' => [ 'force_default' => 'parent_1.0.0' ] where 1.0.0 is the parent version number or 'flags' => [ 'force_default' => 'child_1.0.0' ] where 1.0.0 is the child version number. 

```php
apply_filters( 'mv_trellis_settings', array $theme_settings )
```

**Default**

- Empty array

**Arguments**

- $theme_settings `array` Theme settings to be added to the Trellis Settings page.

------

### mv_trellis_settings_groups

Used to add or modify theme setting groups or tabs.

```php
apply_filters( 'mv_trellis_settings_groups', array $default_groups )
```

**Default**

```php
$groups = [
        'issues'   => __( 'Issues', 'mediavine' ),
        'hooks'    => __( 'Hooks', 'mediavine' ),
        'license'  => __( 'License', 'mediavine' ),
        'pwa'      => __( 'PWA', 'mediavine' ),
        'advanced' => __( 'Advanced', 'mediavine' ),
        'display'  => __( 'Display', 'mediavine' ),
      ];
```

**Arguments**

- $default_groups `array` Key/value pair of setting group slugs and display names. These should correspond to the group column of the settings table.

------

### mv_trellis_settings_update

Used to specify which settings to update.

```php
apply_filters( 'mv_trellis_settings_update', array $theme_settings )
```

**Default**

- self::get_theme_settings()

**Arguments**

- $theme_settings `array` Theme settings to be added or updated on the settings page.

------

### mv_trellis_sidebar_content

HTML string for the sidebar. Used internally to apply lazy loading attributes to images.

```php
apply_filters( 'mv_trellis_sidebar_content', string $sidebar_html, string $sidebar_id )
```

**Default**

- HTML output of the sidebar.

**Arguments**

- $sidebar_html `string` The sidebar HTML.
- $sidebar_id `string` The sidebar ID.

------

### mv_trellis_site_title_logo_alt_text

Alt text used by the site logo. Defaults to the site name.

```php
apply_filters( 'mv_trellis_site_title_logo_alt_text', string $site_name )
```

**Default**

- `get_bloginfo( 'name' )`

**Arguments**

- $site_name `string` Site name.

------

### mv_trellis_site_title_logo_classes

Class names to be added to site logo `<img>`tag.

```php
apply_filters( 'mv_trellis_site_title_logo_classes', array $image_classes, bool $link )
```

**Default**

- `['header-logo-img', 'ggnoads']`

**Arguments**

- $image_classes `array` List of classes to be added to the logo source markup.
- $link `bool` Whether site title/logo output should be wrapped in a link.

------

### mv_trellis_site_title_shortcode

Adjusts the HTML string for the site title displayed in the site footer. Defaults to the site name.

```php
apply_filters( 'mv_trellis_site_title_shortcode', string $output, array $atts )
```

**Default**

- `get_bloginfo( 'name' )`

**Arguments**

- $output `string` Site title output.
- $atts `array` Site title shortcode attributes.

------

### mv_trellis_site_title_text_classes

Adjusts classes for the site title markup.

```php
apply_filters( 'mv_trellis_site_title_text_classes', array $value, bool $link )
```

**Default**

- [ 'header-logo-text']

**Arguments**

- $value `array` Classes to be added to the site title markup.
- $link `bool` If the site title/logo output should be wrapped in a link.

------

### mv_trellis_sw_ignore

Lists the paths to be ignored by the PWA service worker.

```php
apply_filters( 'mv_trellis_sw_ignore', array $ignore_paths )
```

**Default**

- Empty array

**Arguments**

- $ignore_paths `array` List of file paths to ignore.

------

### mv_trellis_the_title

Adjusts the current page/post title.

```php
apply_filters( 'mv_trellis_the_title', string $title, string $before, string $after )
```

**Default**

- The current page/post/archive/cpt title.

**Arguments**

- $title `string` The current page/post/archive title.
- $before `string` Content to be added to the front of the title, usually in some form of markup.
- $after `string` Content to be added to the end of the title, usually in some form of markup.

------

### mv_trellis_top_breadcrumbs_placement

Adjusts the hook targeted to output YOAST SEO breadcrumbs.

```php
apply_filters( 'mv_trellis_top_breadcrumbs_placement', string $default_header_breadcrumb_hook )
```

**Default**

- tha_aside_before_entry_content

**Arguments**

- $default_header_breadcrumb_hook `string` The hook to fire on.

------

### mv_trellis_web_stories_compatibility_styles

Adjusts the CSS styles applied to the Web Story archive pages.

```php
apply_filters( 'mv_trellis_web_stories_compatibility_styles', string $story_archive_styles )
```

**Default**

```css
.post-type-archive-web-story .excerpt {flex: 1 1 360px; margin: 0px auto; max-width: 360px;}
.post-type-archive-web-story .mv-trellis-feed-unit{flex: 1 1 100%;}
.post-type-archive-web-story .pagination{flex: 1 1 100%;}
.post-type-archive-web-story .excerpt-container,.post-type-archive-web-story .excerpt-post-data{display: block;}
.post-type-archive-web-story .excerpt-post-data{text-align:center;}
.post-type-archive-web-story .wp-block-embed__wrapper {margin:0 auto;}
.post-type-archive-web-story .excerpt-photo {display: none;}
```

**Arguments**

- $story_archive_styles `string` CSS styles applied to Web Story archive pages.

------

### mv_trellis_wordpress_link_shortcode

Adjusts the HTML string for the link to WordPress in the site footer.

```php
apply_filters( 'mv_trellis_wordpress_link_shortcode', string $output, array $atts )
```

**Default**

```html
<a href="https://wordpress.org/" target="_blank" rel="noopener nofollow">WordPress</a>
```

**Arguments**

- $output `string` WordPress link output.
- $atts `array` WordPress link shortcode attributes.