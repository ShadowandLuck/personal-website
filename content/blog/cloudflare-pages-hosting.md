---
title: "How to Host Your Hugo Site on Cloudflare Pages"
date: 2024-05-02
description: "A step-by-step guide to deploying your Hugo website on Cloudflare Pages"
categories: ["technology", "tutorials"]
tags: ["hugo", "cloudflare", "hosting", "web development"]
---

# How to Host Your Hugo Site on Cloudflare Pages

[Cloudflare Pages](https://pages.cloudflare.com/) is a fantastic platform for hosting static websites like those built with Hugo. It offers free hosting with unlimited bandwidth, automatic HTTPS, and global CDN distribution. In this guide, I'll walk you through the process of deploying your Hugo site on Cloudflare Pages.

## Prerequisites

Before we begin, make sure you have:

1. A Hugo website ready for deployment
2. A [GitHub](https://github.com/) or [GitLab](https://gitlab.com/) account where your site's code is hosted
3. A [Cloudflare](https://www.cloudflare.com/) account (free tier is sufficient)

## Step 1: Prepare Your Hugo Project for Deployment

Ensure your Hugo project is properly structured and working locally. Run `hugo server` to verify everything looks good.

Make sure your repository includes a `.gitignore` file that excludes the `public/` and `resources/` directories, as these will be generated during the build process.

## Step 2: Set Up Your Git Repository

If you haven't already, push your Hugo project to a GitHub or GitLab repository:

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/yourusername/your-repo-name.git
git push -u origin main
```

## Step 3: Connect to Cloudflare Pages

1. Log in to your Cloudflare account
2. Navigate to the "Pages" section from the dashboard
3. Click "Create a project"
4. Choose "Connect to Git"
5. Select your Git provider (GitHub or GitLab) and authenticate
6. Select your repository from the list

## Step 4: Configure Your Build Settings

Once your repository is connected, you'll need to configure the build settings:

1. **Project name**: Choose a name for your project (this will be part of your default subdomain)
2. **Production branch**: Select your main branch (usually `main` or `master`)
3. **Build settings**:
   - **Framework preset**: Select "Hugo"
   - **Build command**: `hugo --minify`
   - **Build output directory**: `public`
   - **Environment variables** (optional): If you're using a specific Hugo version, add `HUGO_VERSION` with your desired version number (e.g., `0.101.0`)

4. Click "Save and Deploy"

## Step 5: Wait for Deployment

Cloudflare will now build and deploy your site. This process usually takes a minute or two. You can monitor the progress in the deployment logs.

## Step 6: Configure Your Custom Domain (Optional)

If you want to use your own domain instead of the default `*.pages.dev` subdomain:

1. Go to your project in Cloudflare Pages
2. Navigate to "Custom domains"
3. Click "Set up a custom domain"
4. Enter your domain name and follow the instructions

If your domain is already managed by Cloudflare, the setup will be automatic. If not, you'll need to update your DNS settings to point to Cloudflare Pages.

## Step 7: Set Up Continuous Deployment

One of the best features of Cloudflare Pages is automatic deployment when you push changes to your repository. Every time you push to your main branch, Cloudflare will automatically rebuild and deploy your site.

You can also set up preview deployments for pull requests, allowing you to preview changes before merging them into your main branch.

## Troubleshooting Common Issues

### Build Failures

If your build fails, check the build logs for errors. Common issues include:

- Incorrect Hugo version: Specify the correct version in the environment variables
- Missing dependencies: Ensure all required files are in your repository
- Build command errors: Verify your build command is correct

### Custom Domain Issues

If you're having trouble with your custom domain:

- Verify DNS settings are correct
- Check for SSL/TLS certificate issues
- Ensure your domain is properly configured in Cloudflare Pages

## Conclusion

Cloudflare Pages provides a powerful, free platform for hosting Hugo websites with excellent performance and reliability. With the automatic deployment workflow, you can focus on creating content while Cloudflare handles the deployment process.

Happy hosting! 