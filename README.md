# Topic Author Badge

Current version: `v0.1.20`

Author: Longlan

A Discourse theme component that marks posts written by the topic author / original poster.

This component is inspired by [`VaperinaDEV/author-badge-for-topic-posts`](https://github.com/VaperinaDEV/author-badge-for-topic-posts), with simplified settings and Chinese-friendly defaults.

## Features

- Adds a badge to topic author's later posts
- Default label: `楼主`
- Default desktop/mobile position: below user avatar
- Selectable style preset: original, capsule, subtle, solid, or custom
- Separate desktop/mobile labels
- Separate desktop/mobile enable switches
- Optional display on the first post
- Desktop locations:
  - after user names
  - below user names
  - below user avatar
- Mobile locations:
  - after user names
  - below user names
  - below user avatar
- Custom colors, border radius, and font style
- Optional category-specific label overrides

## Settings

- `topic_author_badge_label_desktop`
- `topic_author_badge_label_mobile`
- `topic_author_badge_enable_desktop`
- `topic_author_badge_enable_mobile`
- `topic_author_badge_show_on_first_post`
- `topic_author_badge_location_desktop`
- `topic_author_badge_location_mobile`
- `topic_author_badge_style_preset`
- `topic_author_badge_background`
- `topic_author_badge_text_color`
- `topic_author_badge_border_color`
- `topic_author_badge_border_radius`
- `topic_author_badge_font_style`
- `topic_author_badge_category_overrides`

### Style preset

`topic_author_badge_style_preset` controls the default appearance:

- `original`: upstream/original component look. This is the default.
- `capsule`: rounded pill badge style from this fork's early versions.
- `subtle`: quiet light badge for everyday communities.
- `solid`: stronger filled badge for clearer author emphasis.
- `custom`: use the color and radius settings below the preset field.

### Category overrides

Optional advanced setting. One rule per item:

```text
category-slug:desktop-label:mobile-label
```

Example:

```text
support:Author:OP
video:导演:导演
```

Leave empty to use the global labels.

## Install

Install as a theme component from the Discourse admin UI using this repository URL:

```text
https://github.com/longlannet/discourse-topic-author-badge
```

## Changelog

### v0.1.20

- Fix desktop `below-user-names` disappearing by overriding Discourse core `.topic-meta-data::after` clearfix properties (`visibility`, `height`, `clear`, and font size).

### v0.1.19

- Move desktop `below-user-names` from `.regular.contents::before` into `.topic-meta-data::after`, so the badge belongs to the author metadata area instead of pushing the post body content down.

### v0.1.18

- Fix mobile `below-user-names` placement by returning to `.topic-meta-data::after` while preventing full-width stretching with a separate flex line-break pseudo-element.

### v0.1.17

- Fix mobile `below-user-names` badge becoming full-width by anchoring it to `.names .first::after` instead of `.topic-meta-data::after`.

### v0.1.16

- Simplify mobile locations to stable anchors only: `after-user-names`, `below-user-names`, and `below-user-avatar`.
- Remove mobile `above-user` and `above-avatar` from settings because they rely on fragile positioning in the current Discourse mobile layout.
- Move mobile `below-user-names` to `.topic-meta-data::after` for a more stable username-area placement.

### v0.1.15

- Refine mobile username-area placements for current Discourse mobile DOM:
  - `above-user` now uses `.topic-meta-data::before` with flex wrapping.
  - `below-user-names` now uses `.names::after` with flex order, avoiding `.first::after` inline/ellipsis issues.

### v0.1.14

- Add mobile `below-user-names` location using `.topic-meta-data .names .first::after`, placing the badge directly below the first username line.

### v0.1.13

- Adjust mobile `above-user` to place the badge above the username area instead of above the avatar.
- Add `above-avatar` mobile location to preserve the original component's `.row::before` avatar-top behavior.

### v0.1.12

- Restore mobile `above-user` placement to match the original component: `.row::before` with absolute positioning.

### v0.1.11

- Fix mobile `above-user` placement by attaching the badge to `.topic-body::before` instead of `.row::before`, preventing it from appearing above the avatar.

### v0.1.10

- Refine text centering: keep flex alignment but remove fixed min-height so different positions and font sizes render consistently.

### v0.1.9

- Improve badge text centering by using a flex-centered base badge with stable min-height.

### v0.1.8

- Fix desktop/mobile enable switches when Discourse provides boolean settings to SCSS as string values.

### v0.1.7

- Move desktop/mobile enable switches to the top of the settings list for easier access.

### v0.1.6

- Add separate desktop/mobile enable switches.

### v0.1.5

- Add `subtle` and `solid` style presets.

### v0.1.4

- Add `topic_author_badge_style_preset` so admins can choose the original look, capsule look, or custom colors/radius.

### v0.1.3

- Align selectors, mobile behavior, default placement, and default badge styling with the original component.
- Keep this fork's Chinese-friendly labels and optional first-post setting.

### v0.1.2

- Fix first-post exclusion when `topic_author_badge_show_on_first_post` is disabled.

### v0.1.1

- Fix desktop `below-user-names` location to match the original component placement.

### v0.1.0

- Initial release.

## License

GPL-2.0-or-later.
