# ScheduleAPI Front End Documentation

This documentation provides guidance on setting up and developing the front end of the ScheduleAPI project using Vue.js.

## Table of Contents

1. [Project Structure](#project-structure)
2. [Recommended IDE Setup](#recommended-ide-setup)
3. [Customization](#customization)
4. [Project Setup](#project-setup)
5. [Development](#development)
6. [Building for Production](#building-for-production)
7. [Unit Testing](#unit-testing)
8. [Adding New Features](#adding-new-features)

## Project Structure <a name="project-structure"></a>


- **src/**: Contains the main source code of the Vue.js application.
  - **assets/**: Static assets like images, fonts, etc.
  - **components/**: Reusable Vue components.
  - **router/**: Vue Router configurations.
  - **store/**: Vuex store configurations.
  - **views/**: Vue components representing different views of the application.
  - **App.vue**: Root Vue component.
  - **main.ts**: Entry point of the application.
- **public/**: Contains static files that will be copied directly into the build folder.
- **tests/**: Unit tests folder.
- **.gitignore**: Specifies intentionally untracked files to ignore.
- **package.json**: Configuration file for npm dependencies and scripts.
- **README.md**: Project documentation.
- **vite.config.ts**: Vite configuration file.

## Recommended IDE Setup <a name="recommended-ide-setup"></a>

We recommend using the following setup for an optimal development experience:

- [Visual Studio Code](https://code.visualstudio.com/) with [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) extension (disable Vetur) and [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Customization <a name="customization"></a>

For customization options, refer to the [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup <a name="project-setup"></a>

```sh
npm install

