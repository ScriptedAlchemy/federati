# Federati

> Official Monorepo of software designed to work with Webpack Module Federation
> Build and maintained by the creators of Module Federation


### Workflows set up

- Install: run `yarn`
  - This uses yarn workspaces to manage installation of dependencies for all your packages.
  - This also runs a `postinstall` hook that will validate your monorepo setup (using `Manykpkg`), and set your packages up for dev (using `Preconstruct`)
- Test: run `yarn test`, which will run Jest tests.
- Build: run `yarn build`
  - This uses Preconstruct to build `dist` files from the source of all packages in `/packages` and `/apps`.
  - For any build work you want done outside of Preconstruct building dists, you will need to add to this script.
- Release: run `yarn release`
  - this will run the build command, and then run `changeset publish`
- Clean: run `yarn clean`
  - this uses `Manypkg` to remove the `node_modules` and `dist` folders from each package in the repository, as well as from the root. It can be used to 'clean out' installed/built files to ensure running `yarn` or `build` gets you fresh information.

We strongly recommend using Changesets for versioning as well, here is a [base explanation of the workflow](https://github.com/atlassian/changesets/blob/master/docs/intro-to-using-changesets.md)
