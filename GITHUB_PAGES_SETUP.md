# GitHub Pages Setup Instructions

This guide will help you enable and configure GitHub Pages for this repository.

## Prerequisites

- Repository must be public (or GitHub Pro/Team/Enterprise for private repos)
- Admin access to the repository

## Step-by-Step Setup

### 1. Enable GitHub Pages

1. Navigate to your repository on GitHub: `https://github.com/balakrn/musical-umbrella`
2. Click on **Settings** tab
3. In the left sidebar, click on **Pages** (under "Code and automation")
4. Under **Build and deployment**:
   - **Source**: Select **"GitHub Actions"** from the dropdown
   - This will enable the workflow-based deployment

### 2. Verify Workflow File

The GitHub Actions workflow is already configured in `.github/workflows/pages.yml`. This workflow:
- Automatically deploys on every push to the `main` branch
- Can be manually triggered from the Actions tab
- Uses the official GitHub Pages deployment actions

### 3. Trigger Initial Deployment

You have two options:

#### Option A: Push to Main Branch (Recommended)
```bash
# Merge this PR to main branch
# The workflow will automatically run and deploy
```

#### Option B: Manual Trigger
1. Go to the **Actions** tab in your repository
2. Select **"Deploy to GitHub Pages"** workflow
3. Click **"Run workflow"** button
4. Select the branch (usually `main`)
5. Click **"Run workflow"**

### 4. Access Your Site

After the workflow completes successfully:

**Your site will be available at:** `https://balakrn.github.io/musical-umbrella/`

The workflow typically takes 1-2 minutes to complete.

### 5. Verify Deployment

1. Go to **Actions** tab to see the workflow run
2. Wait for the workflow to complete (green checkmark)
3. Visit `https://balakrn.github.io/musical-umbrella/`
4. You should see your Carnatic Music Lessons website

## Workflow Details

The deployment workflow:
- **Name**: Deploy to GitHub Pages
- **Trigger**: Push to `main` branch or manual dispatch
- **Permissions**: Read contents, write pages, write ID tokens
- **Jobs**: 
  - `build`: Prepares the site for deployment
  - `deploy`: Deploys to GitHub Pages

## Troubleshooting

### Workflow Not Running
- Ensure the workflow file is on the `main` branch
- Check that GitHub Actions are enabled in Settings → Actions

### 404 Error on Site
- Wait a few minutes after first deployment
- Verify the workflow completed successfully
- Check that `index.html` exists in the repository root

### Permission Errors
- Ensure "Read and write permissions" are enabled in Settings → Actions → General → Workflow permissions

## Custom Domain (Optional)

To use a custom domain:
1. Go to Settings → Pages
2. Enter your custom domain in the "Custom domain" field
3. Add appropriate DNS records with your domain provider
4. Enable "Enforce HTTPS" after DNS propagates

## Updating the Site

To update your site:
1. Make changes to `index.html` or other files
2. Commit and push to `main` branch
3. The workflow will automatically rebuild and redeploy

## Additional Resources

- [GitHub Pages Documentation](https://docs.github.com/pages)
- [GitHub Actions Documentation](https://docs.github.com/actions)
- [Configuring a publishing source](https://docs.github.com/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
