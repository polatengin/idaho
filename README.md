# Publishing multiple npm Packages to GitHub Packages

This guide explains the steps required to publish multiple npm packages from the same repository to `GitHub Packages`.

> In this example we will publish two packages from the same repository to `GitHub Packages`. The packages are named `package-1` and `package-2`.

## Prerequisites

- GitHub account
- Repository with the code for the packages
- Node.js and npm

## Steps

- **Set up the repository**: Create a new repository on `GitHub` or use an existing one where your code is hosted. Organize your codebase with separate directories for each package.

- **Configure npm**: Ensure that you have a valid `package.json` file in the root of your repository. This file should contain the necessary metadata for both packages, including their _names_, _versions_, _dependencies_, and other relevant details.

- **Authenticate with GitHub Packages**: To publish packages to `GitHub Packages`, you need to authenticate with a _personal access token_ (_PAT_). Follow these steps to generate a _PAT_:
  - Go to your GitHub [account settings](https://github.com/settings/profile) page
  - Navigate to ["Developer Settings" > "Personal access tokens"](https://github.com/settings/tokens)
  - Click on `Generate new token` and provide the necessary permission (`write:packages`)
  - Once generated, copy the token for later use

- **Configure `.npmrc`**: Create or modify the `.npmrc` file in the root of your repository. Add the following lines, replacing `TOKEN` with the personal access token generated in the previous step:

```plaintext
@your-username:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_authToken=TOKEN
```

- Separate package configurations: In each package's directory within your repository, ensure that you have a separate package.json file that contains the package-specific details and configuration.

- Publish the packages: To publish your packages, follow these steps for each package:

  - Navigate to the package's directory
  - Run the npm publish command

For example, to publish _Package-1_, use the following commands:

```bash
cd ./src/package-1
npm publish
```

Repeat these steps for the second package, changing to its directory and running npm publish.

That's it! Following these steps will allow you to publish multiple npm packages from the same repository to `GitHub Packages`.

Remember to manage the package versions and updates accordingly to avoid any conflicts or issues.
