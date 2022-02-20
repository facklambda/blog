+++
title = "beerlicht pt 2"
description = "the electric boogaloo"

# The date of the post.
# Two formats are allowed: YYYY-MM-DD (2012-10-02) and RFC3339 (2002-10-02T15:00:00Z).
# Do not wrap dates in quotes; the line below only indicates that there is no default date.
# If the section variable `sort_by` is set to `date`, then any page that lacks a `date`
# will not be rendered.
# Setting this overrides a date set in the filename.
date = 2022-02-19

# The last updated date of the post, if different from the date.
# Same format as `date`.

# The weight as defined on the Section page of the documentation.
# If the section variable `sort_by` is set to `weight`, then any page that lacks a `weight`
# will not be rendered.
weight = 0

# A draft page is only loaded if the `--drafts` flag is passed to `zola build`, `zola serve` or `zola check`.
draft = false

# If set, this slug will be used instead of the filename to make the URL.
# The section path will still be used.

# The path the content will appear at.
# If set, it cannot be an empty string and will override both `slug` and the filename.
# The sections' path won't be used.
# It should not start with a `/` and the slash will be removed if it does.
path = "beerlict-pt-2"

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
tags = ["rust", "iot", "art", "ws281x", "leds"]
categories = ["projects"]


# Your own data.
[extra]
+++

I've made leaps and bounds of progress on this project once I decided to start a bit smaller!

Rather than being a bit over-ambitious, which is learning rust without much foundation on a relatively new embedded system (ESP32-C3) with relatively little documentation (it's vastly improved since my last blog post). I readjusted my ambitions and settled on a more realistic goal of getting it all to run on a raspberry pi.
<!-- more -->

Parts list so far:
- ~~ESP32-C3~~
- Raspberry Pi 2b+ (running raspbian)
- string of 25 WS2812b LEDs
- 25 glass bottles
- a milk crate
- 3 dupont wires

---

After spending a few months hoarding glass beverage bottles, I finally amassed the proper amount of correctly sized bottles to fit a 5 by 5 grid in the milk crate. Cutting the daisychained strip of 50 WS2812b LEDs in half and placing one of each of the 25 LEDs into the mouth of each bottle was very simple. Hooking them up to the raspberry pi also proved to be simple, just direct connect the corresponding wires to a 5v pin, a SPI GPIO pin, and a ground pin.

# The Code:
I'm pretty new to writing rust code, and embedded electronics, but I have a basic knowledge of most concepts involved. I again had to recalibrate my expectations for this project. There's no way I'm going to get up and running very quickly if I try to code this all myself, so I'm leaning heavily on [Philipp Schuster's very simple ws281x led driver rust code](https://github.com/phip1611/ws2818-rgb-led-spi-driver). This got me up and running with a nice set of examples and demo code that I could rely on for a quick dopamine rush (I particularly like the way the [pulsating square demo](https://github.com/phip1611/ws2818-rgb-led-spi-driver/blob/main/examples/src/bin/nxn-pulsating-square.rs) looks).

As of writing this post, beerlicht's published code still just a [repo](https://github.com/facklambda/beerlicht) containing Philipp's code.

Next steps for this project will be writing the networking code and the logic that lights each light up based on network activity.


greetz to Philipp, V, and all my friends who've been subjected to me showing this off.