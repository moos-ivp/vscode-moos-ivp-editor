# Contributing to MOOS-IvP Editor

Thank you for your interest in contributing to the MOOS-IvP Editor extension for Visual Studio Code!

## CI/CD Pipeline

This repository uses GitHub Actions for continuous integration and deployment. The workflow automatically:

1. **Builds and packages** the extension on every push and pull request
2. **Publishes to the VSCode Marketplace** when a new release is created

### Setting Up for Publishing

To enable automatic publishing to the Visual Studio Code Marketplace, a repository secret needs to be configured:

#### Required Secret: `VSCE_PAT`

1. **Create a Personal Access Token (PAT)**:
   - Go to [Azure DevOps](https://dev.azure.com/)
   - Navigate to User Settings → Personal Access Tokens
   - Create a new token with the following settings:
     - Organization: All accessible organizations
     - Scopes: Marketplace → Acquire, Manage
   - Copy the generated token

2. **Add the secret to GitHub**:
   - Go to repository Settings → Secrets and variables → Actions
   - Click "New repository secret"
   - Name: `VSCE_PAT`
   - Value: Paste the token from step 1
   - Click "Add secret"

### Publisher Setup

The extension is configured to publish under the `moos-ivp` publisher. Ensure:
- The publisher `moos-ivp` exists in the VSCode Marketplace
- The PAT has permissions to publish under this publisher

### Creating a Release

To publish a new version:

1. Update the version in `package.json`
2. Commit the changes
3. Create a new tag: `git tag v0.0.3`
4. Push the tag: `git push origin v0.0.3`
5. Create a GitHub Release from the tag
6. The CI/CD workflow will automatically publish to the marketplace

## Development

This is a syntax highlighting extension without build dependencies. To develop:

1. Clone the repository
2. Open in VSCode
3. Press F5 to launch the Extension Development Host
4. Test your changes with `.moos`, `.bhv`, `.plug`, or `.meta` files

## Code Style

Please maintain consistency with the existing code style in the repository.
