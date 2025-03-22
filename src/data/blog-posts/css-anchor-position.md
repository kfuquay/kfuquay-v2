---
title: CSS Anchor Positioning
slug: css-anchor
description: Exploring how CSS Anchor Positioning simplifies element placement
publishDate: 15 Mar 2025
---

## What is it?

[CSS Anchor Positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_anchor_positioning) lets you position an element relative to another element—without relying on JavaScript or extra HTML structure.

## Why do we want it?

Right now, achieving this behavior usually requires a mix of CSS and JavaScript:

- Set the containing element to `position: relative`
- Set the target element to `position: absolute`
- Do some math 😵‍💫
  - Use JavaScript to calculate element dimensions
  - Adjust for scrolling and page position

This approach also forces a specific HTML hierarchy—the element you’re positioning must be inside the one you’re positioning it relative to.

CSS Anchor Positioning moves all of this logic into CSS. It’s a more declarative approach, keeping everything in one place and reducing code sprawl. This makes it easier to understand for future developers (including future you). Plus, it skips the math, offloading calculations to the browser.

## When do we get it?

Right now, browser support is limited—[check Can I Use](https://caniuse.com/css-anchor-positioning) for updates.

Good news, though! It was picked up for [Interop 2025](https://github.com/web-platform-tests/interop/blob/main/2025/README.md#css-anchor-positioning), meaning browser vendors are actively working on it this year. Full support is probably still a couple of years away, but in the meantime, there’s a [polyfill from OddBird](https://github.com/oddbird/css-anchor-positioning) that you can use today.

There’s plenty of great content on using this property, but my favorite is [Kevin Powell’s video](https://www.youtube.com/watch?v=DNXEORSk4GU) on combining anchor positioning with [popover](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/popover).
