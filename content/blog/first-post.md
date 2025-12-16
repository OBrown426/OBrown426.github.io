+++
title = "Welcome to My Blog"
date = 2025-12-15
description = "The first post on my new Zola blog"

[taxonomies]
categories = ["meta"]
tags = ["welcome", "zola"]

[extra]
toc = false
+++

Welcome to my blog! This is my first post using Zola with the Radion theme.

<!-- more -->

## About This Blog

This blog is built using [Zola](https://www.getzola.org/), a fast static site generator written in Rust. I'm using the beautiful [Radion theme](https://github.com/micahkepe/radion) which features:

- Light and dark mode support
- Syntax highlighting for code
- Built-in search functionality
- Clean, minimalist design

## Getting Started with Zola

Zola makes it incredibly easy to create a static blog. Here's a quick example of how to create a new post:

```bash
# Create a new post
zola new content/my-new-post.md

# Serve locally
zola serve

# Build for production
zola build
```

## What's Next

I plan to write about various topics including:

1. Software development
2. Technology and tools
3. Personal projects
4. Learning experiences

Stay tuned for more posts!

## Code Example

Here's a simple Rust function to demonstrate syntax highlighting:

```rust
fn greet(name: &str) -> String {
    format!("Hello, {}! Welcome to my blog.", name)
}

fn main() {
    println!("{}", greet("World"));
}
```

Thanks for reading!
