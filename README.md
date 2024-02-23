# ScheduleAPI Front End Documentation

This documentation provides guidance on setting up and developing the front end of the ScheduleAPI project using Vue.js.

## Table of Contents

1. Project Structure
2. Recommended IDE Setup
3. Customization
4. Project Setup
5. Development
6. Building for Production
7. Unit Testing
8. Adding New Features

## Project Structure <a name="project-structure"></a>

```
schedule-api-frontend/
│
├── src/
│   ├── assets/
│   ├── components/
│   ├── router/
│   ├── store/
│   ├── views/
│   ├── App.vue
│   └── main.ts
│
├── public/
├── tests/
├── .gitignore
├── package.json
├── README.md
└── vite.config.ts
```

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
```

## Development <a name="development"></a>

Compile and hot-reload for development:

```sh
npm run dev
```

## Building for Production <a name="building-for-production"></a>

Compile and minify for production:

```sh
npm run build
```

## Unit Testing <a name="unit-testing"></a>

Run unit tests using [Vitest](https://vitest.dev/):

```sh
npm run test:unit
```

## Adding New Features <a name="adding-new-features"></a>

To add new features, follow these steps:

1. Create necessary Vue components in the `src/components/` directory.
2. Update the Vue Router configurations in `src/router/` to include routes for new components.
3. If required, update the Vuex store in `src/store/` to manage state related to the new features.
4. Include any additional assets in the `src/assets/` directory.
5. Integrate any APIs or backend services as needed.

## License

This project is licensed under the [MIT License](LICENSE).
