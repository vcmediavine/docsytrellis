---
title: "Functions"
type: no_toc
weight: 20
description: >
  Trellis provides public functions for child theme developers. You can use them to modify data or functionality in a child theme.
---
You’ll find the function’s name, description, and other pertinent information in the list below.

{{% alert title="Note" %}}
To view the complete function, look for it within Trellis Core’s functions.php file, located in mediavine-trellis/inc/functions.php.
{{% /alert %}}

---

### mv_trellis_get_child_theme

Gets the name of the child theme.

{{% alert title="Note" %}}
Use this function when checking for the existence of Trellis.
{{% /alert %}}

**Return**

- `string|null` Name of the child theme or null if the name is not found.

---

### mv_trellis_is_core

Returns whether Trellis Core is the active theme.

{{% alert title="Note" %}}
Using the WP Core function `is_child_theme()` is more reliable and is available earlier.
{{% /alert %}}

**Return**

- `bool` True if Trellis Core is the active theme, False if a Trellis child theme is active.

---

### mv_trellis_get_template_part

Loads the found template part.

**Parameters**

- $slug `string` Template file (including path) to search for.
- $name `string|array` The `mv_trellis_template_type` will search through the Trellis template hierarchy for the matching template name. Including an array will limit the files to search from what is specified in the array.

**Return**

- `string` The HTML of the matching template part.

---

### mv_trellis_nav_menu

Outputs the nav menu with toggle button support.

**Parameters**

- $args `array` Arguments to be used in the core `wp_nav_menu` function.
- $toggle_btn `bool` Displays the toggle button. Defaults to False.
- $toggle_text `string` Text string to be used in the toggle button. Defaults to “Menu.”
- $toggle_template_part `string` Template part to be used for the toggle button. This overrides `$toggle_text`. Defaults to null.

**Return**

- `string` The HTML containing the navigation menu.

---

### mv_trellis_get_attachment_image_tag

Returns the best resolution image in an `<img>` tag with srcset data.

**Parameters**

- $img_id `int|string` Image attachment ID.
- $img_size `string` Image size. Defaults to large.
- $attributes `array` A key/value array of attributes to be added (such as class). Defaults to none.
- $highest_res `string` The max resolution to allow. Defaults to null.
- $lazy_load `bool` Whether to add lazy load markup to the image. Defaults to True.

**Return**

- `string|null` The HTML `<img>` tag or null if no image is available.

---

### mv_trellis_the_attachment_image_tag

Echoes the best resolution image in an `<img>` tag with srcset data.

**Parameters**

- $img_id `int|string` The image attachment ID.
- $img_size `string` The image size.
- $attributes `array` A Key/value array of attributes added (such as class).
- $highest_res `string` The max resolution allowed.
- $lazy_load `bool` Whether lazy loaded markup is added to the image.

**Return**

- `string|null` The HTML `<img>` tag or null if no image is available.

---

### mvt_adjust_excerpt_image_orientation_res

Returns the specified resolution size for excerpt featured images.

**Parameters**

- $orientation `string` The selected orientation for the image.

**Return**

- `string` The resolution size.

---

### mvt_adjust_featured_post_image_orientation_res

Returns the specificed resolution size of the excerpt featured image for the featured post.

**Parameters**

- $orientation `string` The selected orientation for the image.

**Return**

- `string` The resolution size.

---

### mvt_adjust_excerpt_image_sizes( string $sizes )

Adjusts the sizes attribute value for excerpt thumbnail images.

**Default**

- (max-width: 599px) 300px, 270px

**Parameters**

- $sizes `string` The value of the image sizes attribute.

**Return**

- `string` The adjusted sizes attribute value.

---

### mvt_adjust_featured_post_image_sizes

Adjusts the sizes attribute value for the featured post thumbnail images.

**Default**

- (max-width: 340px) calc(100vw - 40px), (max-width: 450px) calc(100vw - 100px), (max-width: 959px) 350px, (max-width: 1134px) 275px, 350px

**Parameters**

- $sizes `string` The value of the image sizes attribute.

**Return**

- `string` The adjusted sizes attribute value.

---

### mvt_get_image_orientation_res

Appends a filtered resolution size to the image orientation. Ensures the specific resolution size of the image is used.

**Parameters**

- $orientation `string` The selected orientation for the image. Defaults to empty.
- $image_res `string` The selected resolution for the image.

**Return**

- `string`  The orientation with an appended resolution size.

---

### mv_trellis_set_data

Sets data that can be used across template parts.

**Parameters**

- $data_key `string` Key of the data.
- $data_value `mixed` Value of the data.

**Return**

- Not applicable. Sets data for retrieval using `mv_trellis_get_data`.

---

### mv_trellis_get_data

Gets data that has been previously set using the `mv_trellis_set_data` function. This is used for passing data across template parts.

**Default**

- Null, which returns all set data.

**Parameters**

- $data_key `string|null` Key of the data to retrieve. If no key is set, all data is retrieved.

**Return**

- `mixed` Data from a specified key or all data in an `array`.

---

### mv_trellis_remove_data

Removes data from an array that was set using the `mv_trellis_set_data` function. Data in the array is available across template parts.

**Parameters**

- $data_key `string` The key of the data to remove.

**Return**

- Not applicable.

---

### mv_trellis_site_title

Outputs the HTML of the site title and logo.

**Parameters**

- $link `bool` Whether to display the site title and logo wrapped in an anchor tag. Defaults to True.

**Return**

- `string` HTML of the site title and logo.

---

### mv_trellis_is_plugin_active

Checks to see if a plugin is active based on a specified slug.

**Parameters**

- $plugin_slug `string|array` Slug of the plugin or an array of slugs to check.

**Return**

- `bool` True if the plugin is active, false if the plugin is not found.

---

### mv_trellis_get_term_description

Gets the specified term description. Checks for Genesis data if no description is found.

**Parameters**

- $term_id `int` ID of the term. Looks for the current term if an ID is not provided.

**Return**

- `string` HTML of the term description.

---

### mv_trellis_get_featured_post

Gets the ID of the featured/sticky post displayed on the home page.

**Parameters**

- None

**Return**

- `int` The ID of the featured post.

---

### mv_trellis_the_term_description

Echos the term description with optional content before and after. Checks for Genesis data if no description is found.

**Parameters**

- $before `string` Content to prepend to the term description. Defaults to empty.
- $after `string` Content to append to the term description. Defaults to empty.

**Return**

- `string` The term description, complete with any specified before or after content.

---

### mv_trellis_get_asset_url

Returns the absolute path of an asset.

**Parameters**

- $asset_path `string` An optional relative path to the asset. Defaults to empty.

**Return**

- `string` The absolute path to the asset.

---

### mv_trellis_has_flag

Returns whether any specified flags are found in the URL.

**Parameters**

- $flag `string` The flag.

**Return**

- `bool` Whether the specified flag exists in the URL.

---

### mv_trellis_entry_taxonomies

Returns a list of taxonomies, if they exist.

**Parameters**

- $sep `string` The separator to use for the taxonomies. Defaults to comma.

**Return**

- `string` A list of taxonomies with the separator between them.

---

### mv_trellis_entry_tags

Outputs a list of tags, if they exist, with optional content before or after the list.

**Parameters**

- $before `string` The content to display before the tags. Defaults to empty.
- $sep `string` The separator to use between the returned tags. Defaults to comma.
- $after `string` The content to display after the tags. Defaults to empty.

**Return**

- `string` A list of tags with appended and prepended content, using specified separators.

---

### mv_trellis_entry_author

Outputs the entry’s author.

**Parameters**

- None

**Return**

- `string` The author name.

---

### mv_trellis_is_meta_item_enabled

Checks to see if a meta option (like category count or author) is selected in a Post Meta location.

**Parameters**

- $item_slug `string` Slug of the meta item.
- $meta_location `string` Location of where the meta item is set to output. Trelis Core defaults to using `post_meta_top` or `post_meta_bottom` as the possible locations.

**Return**

- `bool` Whether the post meta item is set for the specified location.

---

### mv_trellis_yoast_breadcrumbs

Outputs Yoast Breadcrumbs markup if Yoast SEO is available.

**Parameters**

- None

**Return**

- `string` HTML markup of Yoast breadcrumb data.

---

### mv_trellis_entry_date

Outputs the entry publish date or updated date (if the entry has been updated).

**Parameters**

- None

**Return**

- `string` Publish date or updated date of the entry.

---

### mv_trellis_the_posts_pagination

Displays archive/feed pagination controls using arguments passed by the `mv_trellis_pages_pagination_args` filter.

**Parameters**

- Customize arguments in your functions.php file by using the `mv_trellis_pages_pagination_args` filter. See Filters for more information.

**Return**

- `string` HTML output of the pagination links.

---

### mv_trellis_the_title

Outputs a title (page, author, category, etc.) with optional content before or after.

**Parameters**

- $before `string` Content or markup to be output before the title. Defaults to empty.
- $after `string` Content or markup to be output after the title. Defaults to empty.
- $echo `bool` Whether the title content will be echoed. Defaults to True.

**Return**

- `string` The title, complete with optional content before or after.

---

### mv_trellis_output_sidebar

Outputs the sidebars. Content is first run through the `mv_trellis_sidebar_content` filter.

**Parameters**

- $sidebar_id `string` The sidebar id to process.

**Return**

- `string` HTML content of the specified sidebar.

---

### mv_trellis_get_featured_image_tag

Gets the HTML tag of the featured image.

**Parameters**

- $post_id `int` Optional post ID.
- $attr `array` Attributes array. Defaults to empty.
- $echo `bool` Whether to echo the tag or return. Optional, but defaults to True.

**Return**

- `string|null`  HTML of the featured image or null if `$echo` is false.

---

### mv_trellis_get_wp_kses_post_with_images

Adds image and style related tags (including attributes) to the default list for posts. Used to sanitize Trellis DOM manipulations and image handling.

**Parameters**

- None

**Return**

- `array` A list of image and style tags.

---

### mv_trellis_entry_content_class

Outputs a class attribute for the entry-content container. Includes classes specified by the `mv_trellis_entry_content_classes` filter.

**Parameters**

- $class `string|array` A string or array of additional classes to be added to the entry-content class attribute.

**Return**

- `string` Complete list of classes to be added to the entry-content class attribute.

---

### mv_trellis_purge_all_critical_css

Deletes all site Critical CSS and removes any pending rebuild requests.

**Parameters**

- None

**Return**

- Not applicable

---

### mv_trellis_purge_page_critical_css

Deletes Critical CSS files for a specific post or page.

**Parameters**

- $id `int|string` Post or page id. Used to get the post or page slug when the slug is not provided.
- $slug `string` Post or page slug.

**Return**

- Not applicable.