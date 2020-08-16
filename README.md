## Reproducement steps

1. Generate project using `@vue/cli@4.5.3` on Node v14.8.0:

```console
$ vue init hello-world

Vue CLI v4.5.3
? Please pick a preset:                        Manually select features
? Check the features needed for your project:  Choose Vue version, Babel, TS, PWA, Router, Vuex, CSS Pre-processors, Linter, Unit, E2E
? Choose a version of Vue.js that you wan...   3.x (Preview)
? Use class-style component syntax?            Yes
? Use Babel alongside TypeScript (required...  Yes
? Use history mode for router? (Requires p...  Yes
? Pick a CSS pre-processor (PostCSS, Autop...  Sass/SCSS (with node-sass)
? Pick a linter / formatter config:            Prettier
? Pick additional lint features:               Lint on save
? Pick a unit testing solution:                Jest
? Pick an E2E testing solution:                Cypress
? Where do you prefer placing config for B...  In dedicated config files
? Save this as a preset for future projects?   Yes
? Save preset as:                              typescript-class-component
? Pick the package manager to use when ins...  Yarn
```

<details><summary>Vue CLI preset</summary>

```json
{
  "useTaobaoRegistry": false,
  "packageManager": "yarn",
  "presets": {
    "typescript-class-component": {
      "useConfigFiles": true,
      "plugins": {
        "@vue/cli-plugin-babel": {},
        "@vue/cli-plugin-typescript": {
          "classComponent": true,
          "useTsWithBabel": true
        },
        "@vue/cli-plugin-pwa": {},
        "@vue/cli-plugin-router": {
          "historyMode": true
        },
        "@vue/cli-plugin-vuex": {},
        "@vue/cli-plugin-eslint": {
          "config": "prettier",
          "lintOn": [
            "save"
          ]
        },
        "@vue/cli-plugin-unit-jest": {},
        "@vue/cli-plugin-e2e-cypress": {}
      },
      "vueVersion": "3",
      "cssPreprocessor": "node-sass"
    }
  }
}
```

</details>

2. Serve the app and see the bug behaviour:

```console
$ yarn serve

 DONE  Compiled successfully in 3812ms                                                                                                   2:22:25 PM


  App running at:
  - Local:   http://localhost:8080/

  It seems you are running Vue CLI inside a container.
  Access the dev server via http://localhost:<your container's external mapped port>/

  Note that the development build is not optimized.
  To create a production build, run yarn build.

ERROR in src/router/index.ts:8:5
TS2322: Type 'typeof Home' is not assignable to type 'undefined'.
     6 |     path: "/",
     7 |     name: "Home",
  >  8 |     component: Home
       |     ^^^^^^^^^
     9 |   },
    10 |   {
    11 |     path: "/about",
```

---

# hello-world

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Run your unit tests
```
yarn test:unit
```

### Run your end-to-end tests
```
yarn test:e2e
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
