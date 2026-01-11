# GitHub Publication Steps for bb-component-Skeleton Template

The repository is now **fully prepared and committed locally**. Follow these steps to publish it on GitHub:

## Step 1: Create GitHub Repository

1. Go to https://github.com/new
2. Fill in the following:

   - **Repository name**: `bb-component-Skeleton`
   - **Description**: `A modern Svelte 5 template for building Budibase custom components`
   - **Visibility**: **Public**
   - **Initialize with files**: None (we'll push existing content)

3. Click "Create repository"

## Step 2: Push to GitHub

After creating the repository, run in this directory:

```bash
cd /Users/poirazis/Projects/develop/bb_components/bb_super_components/basic/bb-component-Skeleton

# Update the remote if needed (it's already set to https://github.com/poirazis/bb-component-Skeleton.git)
git remote -v

# Push all commits to GitHub
git push -u origin main
```

## Step 3: Configure as Template Repository

1. Go to **https://github.com/poirazis/bb-component-Skeleton/settings**
2. Scroll to **"Template repository"**
3. Check the box: ✓ **This is a template repository**
4. Click **Save**

This enables the "Use this template" button for users.

## Step 4: Create Develop Branch

1. In GitHub, go to your repository
2. Click the branch dropdown (currently showing "main")
3. Type `develop` and create a new branch from main
4. Go to **Settings → Branches**
5. Under "Default branch", select `develop`
6. Confirm the change

_Note: This allows development to happen on `develop` with releases to `main`_

## Step 5: Configure GitHub Actions

GitHub Actions should automatically detect the workflow file. To verify:

1. Go to **Actions** tab in your repository
2. You should see the `release.yml` workflow listed
3. The workflow will trigger automatically when you push to `main` or manually via workflow_dispatch

## Step 6: Add Topics (Optional)

To improve discoverability:

1. Go to **Settings** → **General**
2. Under "Repository topics", add:
   - `budibase`
   - `budibase-plugin`
   - `component`
   - `svelte`
   - `svelte5`
   - `template`

## Step 7: Update GitHub Pages (Optional)

To host documentation:

1. Go to **Settings** → **Pages**
2. Under "Build and deployment", select:
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/ (root)`

## What's Ready

✅ **Comprehensive README** - Quick start guide and component development instructions  
✅ **CONTRIBUTING.md** - Development setup and contribution guidelines  
✅ **.vscode/settings.json** - Recommended extensions and code formatting  
✅ **GitHub Actions Workflow** - Automatic builds and releases on push to main  
✅ **Complete Structure** - All necessary files for a production Budibase component  
✅ **Simplified Component** - Click counter example with minimal boilerplate  
✅ **Schema Validation** - Proper metadata and settings configuration  
✅ **TypeScript Support** - Full type safety with Svelte 5

## Usage

Once published, users can create new components using your template:

1. Go to https://github.com/poirazis/bb-component-Skeleton
2. Click the green "Use this template" button
3. Create their own repository from your template
4. Follow the README to customize for their component

## Release Workflow

For publishing component versions:

1. **Develop** on the `develop` branch
2. **Update version** in `package.json`
3. **Push to develop** and create a PR to `main`
4. **Merge PR** to `main`
5. **GitHub Actions** automatically:
   - Builds the component
   - Creates a release with the tarball
   - Makes it available for distribution

## Questions?

Refer to the README.md for developer documentation and CONTRIBUTING.md for contribution guidelines.
