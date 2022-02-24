+++
title = "bust"
description = "bus timetables in your terminal"

# The date of the post.
# Two formats are allowed: YYYY-MM-DD (2012-10-02) and RFC3339 (2002-10-02T15:00:00Z).
# Do not wrap dates in quotes; the line below only indicates that there is no default date.
# If the section variable `sort_by` is set to `date`, then any page that lacks a `date`
# will not be rendered.
# Setting this overrides a date set in the filename.
date = 2022-02-20

# The last updated date of the post, if different from the date.
# Same format as `date`.

# The weight as defined on the Section page of the documentation.
# If the section variable `sort_by` is set to `weight`, then any page that lacks a `weight`
# will not be rendered.
# weight = 0

# A draft page is only loaded if the `--drafts` flag is passed to `zola build`, `zola serve` or `zola check`.
draft = false

# If set, this slug will be used instead of the filename to make the URL.
# The section path will still be used.

# The path the content will appear at.
# If set, it cannot be an empty string and will override both `slug` and the filename.
# The sections' path won't be used.
# It should not start with a `/` and the slash will be removed if it does.
# path = "bust-pt-1"

# Use aliases if you are moving content but want to redirect previous URLs to the
# current one. This takes an array of paths, not URLs.

# When set to "true", the page will be in the search index. This is only used if
# `build_search_index` is set to "true" in the Zola configuration and the parent section
# hasn't set `in_search_index` to "false" in its front matter.
in_search_index = true

# Template to use to render this page.
# template = "page.html"

# The taxonomies for this page. The keys need to be the same as the taxonomy
# names configured in `config.toml` and the values are an array of String objects. For example,
# tags = ["rust", "web"].
[taxonomies]
tags = ["rust", "cli", "gtfs", "bus", "transit"]
categories = ["projects"]

+++

I've recently been working on a fun project that should be a useful general-utility CLI app that can parse [GTFS](https://gtfs.org/) data for arbitrary transit providers (so long as they publish GTFS data!). I would like to roll this project into a bigger one for displaying timestables on an actual display.

<!-- more -->


The project is currently named ['bust'](https://github.com/facklambda/bust) which is a bit crass, but I like it so I'm sticking with it for the time being.

Currently the major dependencies of the app are [gtfs_structure](https://github.com/rust-transit/gtfs-structure) and [clap](https://github.com/clap-rs/clap). I will likely need to write some code that will be heavily reliant on [reqwest](https://github.com/seanmonstar/reqwest) in order to implement a feature that polls transit provider specific APIs (in this case, [metrotransit's nextripv2 api](https://svc.metrotransit.org/swagger/index.html?urls.primaryName=NexTrip%20API%20-%20v2)).

Currently I'm facing a problem with parsing the gtfs data in a timely manner. On my Raspberry Pi it takes about 30 seconds to parse the gtfs data into structs and the print out statistics regarding them. I believe this can be fine tuned, but don't know exactly how at this time.


greetz to fellow bus riding friends, the strange amount of european transit app developers who like to use Rust, my partner V for putting up with my [rubber duck debugging](https://en.wikipedia.org/wiki/Rubber_duck_debugging)