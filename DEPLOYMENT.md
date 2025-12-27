# GitHub Pages Deployment Guide

This guide explains how to deploy the OpenAPI documentation to GitHub Pages.

## Prerequisites

- A GitHub repository
- GitHub Actions enabled (enabled by default for public repos)

## Setup Steps

### 1. Enable GitHub Pages

1. Go to your repository on GitHub
2. Navigate to **Settings** → **Pages**
3. Under **Source**, select **"GitHub Actions"**
4. Save the settings

### 2. Push Your Code

The deployment workflow is configured to run automatically when you push to the `main` branch:

```bash
git add .
git commit -m "Add GitHub Pages deployment"
git push origin main
```

### 3. Monitor Deployment

1. Go to the **Actions** tab in your repository
2. You should see the "Deploy to GitHub Pages" workflow running
3. Wait for it to complete (usually takes 1-2 minutes)

### 4. Access Your Documentation

Once deployment is complete, your documentation will be available at:

```
https://<your-username>.github.io/<repository-name>/
```

For example, if your repository is `https://github.com/writdev-alt/openapi-specs-v1`, your docs will be at:
```
https://github.com/writdev-alt/openapi-specs-v1
```

## Manual Deployment

You can also manually trigger the deployment:

1. Go to the **Actions** tab
2. Select **"Deploy to GitHub Pages"** workflow
3. Click **"Run workflow"**
4. Select the branch (usually `main`)
5. Click **"Run workflow"** button

## Workflow Details

The deployment workflow:

1. **Checks out** your code
2. **Sets up** Node.js 20
3. **Installs** dependencies using `npm ci`
4. **Builds** the documentation using `npm run build`
5. **Deploys** to GitHub Pages

## Troubleshooting

### Workflow Fails

- Check the Actions tab for error messages
- Ensure `package.json` and `package-lock.json` are committed
- Verify Node.js version compatibility

### Pages Not Updating

- Wait a few minutes for GitHub to propagate changes
- Clear your browser cache
- Check the Actions tab to ensure deployment completed successfully

### 404 Error

- Ensure GitHub Pages is enabled in repository settings
- Verify the source is set to "GitHub Actions"
- Check that the workflow completed successfully

## Custom Domain (Optional)

If you want to use a custom domain:

1. Add a `CNAME` file in the `dist/` directory with your domain
2. Update your domain's DNS settings to point to GitHub Pages
3. Configure the custom domain in repository Settings → Pages

Note: You'll need to modify the build process to include the CNAME file, or add it manually after build.
