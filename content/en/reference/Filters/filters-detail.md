---
tags: ["filters"]
title: "Filters Detail"
linkTitle: "Filters Detail"
type: no_toc
weight: 30
description: >
  A detailed list of available filters in Trellis showing the filter name, description, syntax, default values, and arguments.
---

### mvt_processing_css_status_timeout
Sets the timeout period for the Processing state in Critical CSS.

```php
apply_filters( 'mvt_processing_css_status_timeout', int $value)
```

**Default**
- 7200 seconds (2 hours) from current time

**Arguments**
- $value `int` The amount of time measured in seconds since the Unix Epoch (January 1 1970 00:00:00 GMT).

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

Applied to the height attribute on the About Widget IMG tag.

```php
apply_filters('mv_trellis_about_widget_image_height', int $height)
```

**Default**

- 100

**Arguments**

- $height: `int` The height of the About Widget image in pixels.

------

### mv_trellis_about_widget_image_width

Applied to the width attribute on the About Widget IMG tag.

```php
apply_filters( 'mv_trellis_about_widget_image_width', int $width)
```

**Default**

- 100

**Arguments**

- $width `int` The width of the About Widget image in pixels. VERIFY pixels

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