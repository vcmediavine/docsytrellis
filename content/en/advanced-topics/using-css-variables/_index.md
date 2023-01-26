---
title: "Using CSS Variables"
type: docs
weight: 40
description: >
  Trellis uses CSS variables to control how font, color, and layout spacing settings are applied to the Trellis Core and Bamboo, Birch, and Wisteria child themes. 
---
By using CSS variables in your own child theme, you can make it easy for publishers to update CSS styles using the Mediavine Trellis Dashboard.

## How CSS Variables Work

Trellis’ default CSS stylesheet incorporates all of the settings shown in the table below. If you want to make use of a setting color or font in a different part of your theme, you’ll need to reference a Trellis CSS variable.

{{% alert color="warning" title="Important" %}}
Do not redeclare any Trellis CSS variables. Doing so will break Trellis functionality.
{{% /alert %}}

The syntax to use a CSS variable is:

```css
var(--trellis-variable-name, #optional-fallback-value)
```

For example, if using the Trellis Primary color as the background for a div element (with a fallback value of white), you would use:

```css
div { background-color: var(--mv-trellis-color-primary, #ffffff); }
```

{{% alert title="Note" %}}
A [Sass](https://sass-lang.com/) mixin is included in Trellis Core and Mediavine child themes. This mixin will provide fallback for browsers that don’t support CSS variables. For a complete list of browsers that support CSS variables, see [https://www.lambdatest.com/web-technologies/css-variables](https://www.lambdatest.com/web-technologies/css-variables).
{{% /alert %}}

## List of Trellis CSS Variables

This table represents a full list of CSS variables available in Trellis.

| CSS Variable | Description | Default Value |
| --- | --- | --- |
| `--mv-trellis-color-heading` | Applied to Site Title text when there’s not a logo. | #243746 |
| `--mv-trellis-color-link` | Applied to:<br />- Link text default color<br />- Link icon default fill color<br />- Button default background color | `--mv-trellis-color-primary` |
| `--mv-trellis-color-link-hover` | Applied to:<br />- Link text default hover color<br />- Link icon default hover fill cover<br />- Button default hover background color | `--mv-trellis-color-secondary` |
| `--mv-trellis-color-primary` | Sets a main color for use in child themes. Trellis defaults to using this color for links, buttons, and other elements in the Trellis Core theme and in Birch, Wisteria, and Bamboo. | #243746 |
| `--mv-trellis-color-secondary` | Sets an alternate color for use in child themes. Trellis defaults to using this color for hover effects, alternate buttons, and other secondary elements in the Trellis Core theme and in Birch, Wisteria, and Bamboo. | #243745 |
| `--mv-trellis-color-background-accent` | Sets the background color of some elements like page and post headers in the Trellis Core theme and in Birch and Wisteria. <br /><br />This setting is not used in the Bamboo child theme.<br /><br />Theme support parameter:<br />`mv_trellis_background_accent_color` | #fafafa |
| `--mv-trellis-font-body` | Sets the font of the body element. Select a Web Safe font for best performance. | System Default (Web Safe) |
| `--mv-trellis-font-heading` | Sets the font for all headings. Select a Web Safe font for best performance. | System Default (Web Safe) |
| `--mv-trellis-font-size` | Sets the font size for the body element. | Medium (18px) |
| `--mv-trellis-font-size-ex-sm` | A font size derived from mv-trellis-font-size. | font-size * 0.667 |
| `--mv-trellis-font-size-lg` | A font size derived from mv-trellis-font-size. | font-size * 1.125 |
| `--mv-trellis-font-size-sm` | A font size derived from mv-trellis-font-size. | font-size * 0.875 |
| `--mv-trellis-gutter` | Adjusts the margins between key layout elements like the primary content, sidebar, and widgets. The following defaults are used:<br /><br />Compact = 10px<br />Comfortable = 20px | Comfortable |
| `--mv-trellis-gutter-double` | A gutter value derived from mv-trellis-gutter. | gutter * 2 |
| `--mv-trellis-gutter-large` | A gutter value derived from mv-trellis-gutter. | gutter * 2.5 |
| `--mv-trellis-gutter-small` | A gutter value derived from mv-trellis-gutter. | floor(gutter/2) |
| `--mv-trellis-h1-font-color` | Sets the color of all H1 headings in the Trellis Core theme and Bamboo.<br /><br />This setting is not used in the Wisteria and Birch child themes.<br /><br />Theme support parameter:<br />`mv_trellis_headings_control` | #000 |
| `--mv-trellis-h1-font-size` | Sets the default size for H1 headings.<br /><br />Full options include:<br />- Small: 24px<br />- Medium: 36px<br />- Large: 42px<br />- X-Large: 56px<br /><br />Theme support parameter: <br />`mv_trellis_headings_control` | Medium (36px) |
| `--mv-trellis-h2-font-size` | Adjusts the sizes of H2 through H6 elements based on the H1 size. The following conversions are used:<br /><br />Theme support parameter: <br /> `mv_trellis_headings_control`  | H1 size * 0.75 (rem) |
| `--mv-trellis-h3-font-size` | Adjusts the sizes of H2 through H6 elements based on the H1 size. The following conversions are used:<br /><br />Theme support parameter: <br /> `mv_trellis_headings_control`  | H1 size * 0.67 (rem) |
| `--mv-trellis-h4-font-size` | Adjusts the sizes of H2 through H6 elements based on the H1 size. The following conversions are used:<br /><br />Theme support parameter: <br /> `mv_trellis_headings_control`  | H1 size * 0.63 (rem) |
| `--mv-trellis-h5-font-size` | Adjusts the sizes of H2 through H6 elements based on the H1 size. The following conversions are used:<br /><br />Theme support parameter: <br /> `mv_trellis_headings_control`  | H1 size * 0.56 (rem) |
| `--mv-trellis-h6-font-size` | Adjusts the sizes of H2 through H6 elements based on the H1 size. The following conversions are used:<br /><br />Theme support parameter: <br /> `mv_trellis_headings_control`  | H1 size * 0.5 (rem) |
| `--mv-trellis-heading-font-color` | Sets the color of all H2 to H6 elements to match the H1 color setting in the Trellis Core theme and Bamboo.<br /><br />This setting is not used in the Wisteria and Birch child themes.<br /><br />Theme support parameter: <br />`mv_trellis_headings_control` | #000 |
| `--mv-trellis-max-logo-size` | Sets the max logo height value that can be shown in the header.<br /><br />Full options include:<br />- Small (50px)<br />- Medium (75px)<br />- Large (100px)<br />- Extra Large (150px) | Extra Large (150px) |

## Disabling All Trellis CSS Styling

If you’d like to start from scratch and discard all default Trellis Core CSS styling, add the following code in your `functions.php` file:

{{% alert color="warning" title="Important" %}}
Disabling the default Trellis CSS styles will require you to define all layout and styling in your own CSS files.
{{% /alert %}}

```php
/** Turn Off Trellis Parent Theme CSS **
 * Use add_filter to remove all Trellis parent theme CSS definitions.
*/

 add_filter( 'mv_trellis_enqueue_main_style', '__return_false' );
```