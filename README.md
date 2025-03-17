# My Personal Website

This is a personal website built with [Hugo](https://gohugo.io/) using the [Gallery theme](https://themes.gohugo.io/themes/hugo-theme-gallery/) by Nico Kaiser. The site is designed to showcase photos and blog posts, and is hosted on [Cloudflare Pages](https://pages.cloudflare.com/).

## Features

- Photo galleries with lightbox functionality
- Blog section for articles and tutorials
- Responsive design that works on all devices
- Fast loading times thanks to Hugo's static site generation
- Global CDN distribution via Cloudflare Pages

## Local Development

To run this site locally, you need to have Hugo installed. Follow these steps:

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/personal-website.git
   cd personal-website
   ```

2. Initialize and update the theme submodule:
   ```bash
   git submodule update --init --recursive
   ```

3. Start the Hugo development server:
   ```bash
   hugo server -D
   ```

4. Open your browser and navigate to http://localhost:1313

## Adding Content

### Adding a New Photo Album

1. Create a new directory in the `content` folder:
   ```bash
   mkdir -p content/your-album-name
   ```

2. Create an `index.md` file in the new directory with front matter:
   ```markdown
   ---
   title: "Your Album Title"
   date: 2024-05-01
   description: "Description of your album"
   categories: ["category1", "category2"]
   tags: ["tag1", "tag2"]
   ---

   Your album description goes here.
   ```

3. Add your photos to the same directory.

### Adding a Blog Post

Create a new markdown file in the `content/blog` directory:

```markdown
---
title: "Your Blog Post Title"
date: 2024-05-01
description: "Description of your blog post"
categories: ["category1", "category2"]
tags: ["tag1", "tag2"]
---

Your blog post content goes here.
```

## Deployment

This site is configured to be deployed on Cloudflare Pages. When you push changes to the main branch, Cloudflare Pages will automatically build and deploy the site.

## License

This project is licensed under the MIT License - see the LICENSE file for details. 