+++
title = "beerlicht"
description = "will-o'-the-WISP"

# The date of the post.
# Two formats are allowed: YYYY-MM-DD (2012-10-02) and RFC3339 (2002-10-02T15:00:00Z).
# Do not wrap dates in quotes; the line below only indicates that there is no default date.
# If the section variable `sort_by` is set to `date`, then any page that lacks a `date`
# will not be rendered.
# Setting this overrides a date set in the filename.
date = 2021-09-14

# The last updated date of the post, if different from the date.
# Same format as `date`.

# The weight as defined on the Section page of the documentation.
# If the section variable `sort_by` is set to `weight`, then any page that lacks a `weight`
# will not be rendered.
weight = 0

# A draft page is only loaded if the `--drafts` flag is passed to `zola build`, `zola serve` or `zola check`.
draft = true

# If set, this slug will be used instead of the filename to make the URL.
# The section path will still be used.

# The path the content will appear at.
# If set, it cannot be an empty string and will override both `slug` and the filename.
# The sections' path won't be used.
# It should not start with a `/` and the slash will be removed if it does.
path = "beerlict"

# Use aliases if you are moving content but want to redirect previous URLs to the
# current one. This takes an array of paths, not URLs.

# When set to "true", the page will be in the search index. This is only used if
# `build_search_index` is set to "true" in the Zola configuration and the parent section
# hasn't set `in_search_index` to "false" in its front matter.
in_search_index = true

# Template to use to render this page.
template = "page.html"

# The taxonomies for this page. The keys need to be the same as the taxonomy
# names configured in `config.toml` and the values are an array of String objects. For example,
# tags = ["rust", "web"].
[taxonomies]
tags = ["rust", "iot", "art"]

# Your own data.
[extra]
+++

I've started on a fun little art project based losely off of [noisebridge's Flaschen Taschen](https://www.noisebridge.net/wiki/Flaschen_Taschen) and [c-base's Mate-Light](https://matelight.rocks).

My twist on the project is that it will be an ambient light that reacts to traffic on the local network (and maybe even the wide area network).
<!-- more -->

Parts list so far:
- ESP32-C3
- string of 25 WS2812b LEDs
- 25 glass bottles
- a milk crate
- 3 dupont wires

---
