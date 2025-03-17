# Deploying to Cloudflare Pages

This document provides step-by-step instructions for deploying this Hugo website to Cloudflare Pages.

## Prerequisites

1. A [GitHub](https://github.com/) or [GitLab](https://gitlab.com/) account
2. A [Cloudflare](https://cloudflare.com/) account
3. Your Hugo website repository (this repository)

## Step 1: Push Your Repository to GitHub/GitLab

If you haven't already, create a new repository on GitHub or GitLab and push your code:

```bash
# If you're using GitHub
git remote add origin https://github.com/yourusername/personal-website.git
git push -u origin main

# If you're using GitLab
git remote add origin https://gitlab.com/yourusername/personal-website.git
git push -u origin main
```

## Step 2: Connect to Cloudflare Pages

1. Log in to your Cloudflare account
2. Navigate to the "Pages" section from the dashboard
3. Click "Create a project"
4. Choose "Connect to Git"
5. Select your Git provider (GitHub or GitLab) and authenticate
6. Select your repository from the list

## Step 3: Configure Build Settings

Configure the build settings for your project:

1. **Project name**: Choose a name for your project (e.g., "my-personal-gallery")
2. **Production branch**: Select your main branch (usually `main` or `master`)
3. **Build settings**:
   - **Framework preset**: Select "Hugo"
   - **Build command**: `hugo --minify`
   - **Build output directory**: `public`
   - **Environment variables**: Add `HUGO_VERSION` with the value `0.145.0` (or your current Hugo version)

4. Click "Save and Deploy"

## Step 4: Wait for Deployment

Cloudflare will now build and deploy your site. This process usually takes a minute or two. You can monitor the progress in the deployment logs.

## Step 5: Configure Custom Domain (Optional)

If you want to use your own domain instead of the default `*.pages.dev` subdomain:

1. Go to your project in Cloudflare Pages
2. Navigate to "Custom domains"
3. Click "Set up a custom domain"
4. Enter your domain name and follow the instructions

If your domain is already managed by Cloudflare, the setup will be automatic. If not, you'll need to update your DNS settings to point to Cloudflare Pages.

## Step 6: Continuous Deployment

Cloudflare Pages automatically sets up continuous deployment. Every time you push changes to your main branch, Cloudflare will automatically rebuild and deploy your site.

## Troubleshooting

If you encounter any issues during deployment, check the build logs in Cloudflare Pages for specific error messages. Common issues include:

- Incorrect Hugo version: Make sure the `HUGO_VERSION` environment variable matches the version you're using locally
- Missing dependencies: Ensure all required files are in your repository
- Build command errors: Verify your build command is correct

## Additional Resources

- [Cloudflare Pages Documentation](https://developers.cloudflare.com/pages/)
- [Hugo Documentation](https://gohugo.io/documentation/)
- [Gallery Theme Documentation](https://themes.gohugo.io/themes/hugo-theme-gallery/) 