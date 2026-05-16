# Publishing to the VS Code Marketplace

## Prerequisites

Install the VS Code Extension CLI (`vsce`) if you haven't already:

```
npm install -g @vscode/vsce
```

## Publish a new version

1. Bump the version in [package.json](package.json) (follows semver: `major.minor.patch`).

2. Package the extension:

```
vsce package
```

This produces a `seafloor-dark-<version>.vsix` file in the project root.

3. Go to the [publisher management page](https://marketplace.visualstudio.com/manage/publishers/timdestan) and click **Upload extension**, then select the `.vsix` file. The new version should appear on the marketplace within a few minutes.

## Test locally before publishing

Install the `.vsix` locally to verify it before uploading:

```
code --install-extension seafloor-dark-<version>.vsix
```

## Debugging during development

Use F5 in VS Code to launch an Extension Development Host with the current theme files loaded. After editing the theme JSON, run **Developer: Reload Window** in that host window to see changes without repackaging.
