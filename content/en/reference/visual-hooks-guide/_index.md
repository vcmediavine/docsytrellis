---
title: "Visual Hooks Guide"
type: docs
weight: 40
description: >
  The Visual Hooks Guide contains diagrams showing where Trellis hooks appear within the Trellis Core templates.
---
Use this guide to see which hooks appear within or before major HTML elements.

{{% alert title="Note" %}}
These diagrams show the hooks as coded in the Trellis Core theme. Other themes (such as Bamboo, Birch, and Wisteria) may vary from these diagrams.
{{% /alert %}}

## Helpful Information
- Hooks are fired within custom Trellis functions. Those functions are what is shown in the diagrams.
- Not all available Trellis hooks are displayed in the diagrams. See Hooks for a complete list.
- Top-level elements such as `<html>`, `<head>`, and `<body>` are not shown in the diagrams. Hooks that apply to those areas are shown at the top of Header Hooks.

## Diagrams

### Header Area

- [Header Hooks](Trellis-Visual-Hooks-Guide-Header.png)

### Content Area 

- [Content-Latest Posts Page Hooks](Trellis-Visual-Hooks-Guide-Content-Latest-Posts.png)
- [Content-Feed Page Hooks](Trellis-Visual-Hooks-Guide-Content-Feed.png)
- [Content-Single Page Hooks](Trellis-Visual-Hooks-Guide-Content-Single.png)
- [Content-Full-Width Page Hooks](Trellis-Visual-Hooks-Guide-Content-Full-Width-Page.png)

### Footer Area

- [Footer Hooks](Trellis-Visual-Hooks-Guide-Footer.png)

## What’s Next?

- See the [Visual Markup Guide]({{< ref "visual-markup-guide" >}}) to see Trellis Core page layouts without the hooks.
- Read about all available Trellis hooks in the [Hooks]({{< ref "hooks" >}}) article.