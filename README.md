# Topic Author Badge

Current version: `v0.1.4`

Author: Longlan

A Discourse theme component that marks posts written by the topic author / original poster.

This component is inspired by [`VaperinaDEV/author-badge-for-topic-posts`](https://github.com/VaperinaDEV/author-badge-for-topic-posts), with simplified settings and Chinese-friendly defaults.

## Features

- Adds a badge to topic author's later posts
- Default label: `楼主`
- Default desktop/mobile position: below user avatar
- Selectable style preset: original, capsule, or custom
- Separate desktop/mobile labels
- Optional display on the first post
- Desktop locations:
  - after user names
  - below user names
  - below user avatar
- Mobile locations:
  - after user names
  - above user
  - below user avatar
- Custom colors, border radius, and font style
- Optional category-specific label overrides

## Settings

- `topic_author_badge_label_desktop`
- `topic_author_badge_label_mobile`
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
