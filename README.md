# cms-vue-module-template [beta]
Template for creating [HubSpot](https://www.hubspot.com) module using [Vue](https://vuejs.org/) for use in the [HubSpot CMS](https://www.hubspot.com/products/cms).

- Uses Vue version 2(currently 2.6)
- Supports Vue SFC([Single File Components](https://vuejs.org/v2/guide/single-file-components.html))

## Generating a Project

In order to generate a Vue project using the cms-vue-module-template you will first need to have the [vue-cli](https://cli.vuejs.org/) installed...
```
yarn global add vue-cli
```

Then to generate the project from this template...
```
vue init HubSpot/cms-vue-module-template
```

Note: In order to run the commands within the project's [package.json](template/package.json) you will need to set up the [HubSpot CLI](https://www.npmjs.com/package/@hubspot/cms-cli).

#### Set up HubSpot CMS CLI ([`@hubspot/cms-cli`](https://www.npmjs.com/package/@hubspot/cms-cli))
- A config file named `hubspot.config.yml` will also be needed.  The config can be at the project level or higher up in the directory tree.
- Be sure to set a `defaultPortal` in your `hubspot.config.yml` to which you'd like the built app files to sync.

For more information on the HubSpot local development tools, see [Local Development Tooling: Getting Started](https://designers.hubspot.com/docs/tools/local-development).

## Running the Project
- Run `npm start` or `yarn start` to automatically upload your module to the `defaultPortal` listed in the `hubspot.config.yml`.
- The module can now be embedded within a page or any drag-and-drop (`dnd_area`) enabled template in your portal. Simply a, and add the module(see snippet below).
  ```
  {% module "vue_module" path="./{{ your project name here }}/modules/app" label="Vue Module" %}
  ```

### package.json scripts
- `start` : Builds project with webpack, uploads to your `defaultPortal` specified in `hubspot.config.yml` and watches for changes via [`@hubspot/webpack-cms-plugins/HubSpotAutoUploadPlugin`](https://www.npmjs.com/package/@hubspot/webpack-cms-plugins).
- `build` : Clears `/dist` contents and builds project into `/dist`.
- `deploy` : Clears `/dist` contents, builds project into `/dist`, and uploads to via [`@hubspot/cms-cli`](https://www.npmjs.com/package/@hubspot/cms-cli).
- `lint` : Lints CSS, JS, and JSON files via `eslint` ([documentation](https://eslint.org/docs/user-guide/configuring)) and checks for formatting via `prettier`([documentation](https://prettier.io/docs/en/configuration.html)) in `src`.
  - For configs, see `prettier.config.js` and `eslintrc.js`.
- `prettier:write` : Formats JS and JSON files in `src`.
  - For configs, see `prettier.config.js`.
