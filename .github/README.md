# GitHub Workflows for Vibra Wiki

## Deployment to GitHub Pages

This repository uses GitHub Actions to automate the deployment of the Docusaurus site to GitHub Pages.

### Deployment Workflow

The `.github/workflows/deploy.yml` file defines a workflow that is automatically triggered when a push is made to the `main` branch. This workflow:

1. Sets up a Node.js environment
2. Installs project dependencies
3. Builds the Docusaurus site
4. Deploys the generated files to the `gh-pages` branch

### Required Configuration in GitHub

To ensure the deployment works correctly, you must configure the following in your GitHub repository:

1. Go to the repository settings: `Settings > Actions > General`
2. In the "Workflow permissions" section, select "Read and write permissions" and save the changes
3. Go to the Pages settings: `Settings > Pages`
4. In "Source", select "Deploy from a branch"
5. In "Branch", select `gh-pages` and the root folder (`/`), then save the changes

### Manual Deployment

If you prefer to perform a manual deployment, you can use the following command:

```bash
GIT_USER=<your-github-username> USE_SSH=true npm run deploy
```

```bash
$env:GIT_USER="<your-github-username>"
$env:GIT_PASS="<your-github-token>"
npm run deploy
```

Replace `<your-github-username>` with your GitHub username.

### Troubleshooting

If you encounter issues with the deployment:

1. Check the GitHub Actions logs in the "Actions" tab of the repository
2. Ensure that the configurations in `docusaurus.config.ts` are correct (url, baseUrl, organizationName, projectName)
3. Confirm that GitHub Actions permissions are configured correctly