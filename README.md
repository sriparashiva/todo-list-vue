<div align="center">
<h1 align="center">
<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/ec559a9f6bfd399b82bb44393651661b08aaf7ba/icons/folder-markdown-open.svg" width="100" />
<br>todo-list-vue
</h1>
<h3>◦ Organize with ease: Todo List Vue</h3>
<h3>◦ Developed with the software and tools listed below.</h3>

<p align="center">
<img src="https://img.shields.io/badge/esbuild-FFCF00.svg?style&logo=esbuild&logoColor=black" alt="esbuild" />
<img src="https://img.shields.io/badge/SVG-FFB13B.svg?style&logo=SVG&logoColor=black" alt="SVG" />
<img src="https://img.shields.io/badge/JavaScript-F7DF1E.svg?style&logo=JavaScript&logoColor=black" alt="JavaScript" />
<img src="https://img.shields.io/badge/HTML5-E34F26.svg?style&logo=HTML5&logoColor=white" alt="HTML5" />
<img src="https://img.shields.io/badge/PostCSS-DD3A0A.svg?style&logo=PostCSS&logoColor=white" alt="PostCSS" />

<img src="https://img.shields.io/badge/Sass-CC6699.svg?style&logo=Sass&logoColor=white" alt="Sass" />
<img src="https://img.shields.io/badge/Vite-646CFF.svg?style&logo=Vite&logoColor=white" alt="Vite" />
<img src="https://img.shields.io/badge/Vue.js-4FC08D.svg?style&logo=vuedotjs&logoColor=white" alt="Vue.js" />
<img src="https://img.shields.io/badge/JSON-000000.svg?style&logo=JSON&logoColor=white" alt="JSON" />
<img src="https://img.shields.io/badge/Markdown-000000.svg?style&logo=Markdown&logoColor=white" alt="Markdown" />
</p>
<img src="https://img.shields.io/github/languages/top/sriparashiva/todo-list-vue?style&color=5D6D7E" alt="GitHub top language" />
<img src="https://img.shields.io/github/languages/code-size/sriparashiva/todo-list-vue?style&color=5D6D7E" alt="GitHub code size in bytes" />
<img src="https://img.shields.io/github/commit-activity/m/sriparashiva/todo-list-vue?style&color=5D6D7E" alt="GitHub commit activity" />
<img src="https://img.shields.io/github/license/sriparashiva/todo-list-vue?style&color=5D6D7E" alt="GitHub license" />
</div>

---

## 📒 Table of Contents
- [📒 Table of Contents](#-table-of-contents)
- [📍 Overview](#-overview)
- [⚙️ Features](#-features)
- [📂 Project Structure](#project-structure)
- [🧩 Modules](#modules)
- [🚀 Getting Started](#-getting-started)
- [🗺 Roadmap](#-roadmap)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)
- [👏 Acknowledgments](#-acknowledgments)

---


## 📍 Overview

The project is a Todo List application built using Vue.js. It enables users to add, remove, and edit tasks, mark tasks as completed, filter tasks based on their completion status, clear all completed tasks, and toggle the completion status of all tasks at once. The application's main purpose is to provide a user-friendly interface for managing and organizing tasks efficiently, offering convenience and productivity enhancement.

---

## ⚙️ Features

| Feature                | Description                                                                                                                                                                                                      |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **⚙️ Architecture**     | The system follows a component-based architecture using Vue.js framework, with the main app logic defined in `src/App.vue`. It utilizes data binding to handle state and UI rendering.                          |
| **📖 Documentation**   | The project lacks comprehensive documentation, but the codebase has meaningful variable and function names, making the code understandable. Certain sections may benefit from additional comments and explanation. |
| **🔗 Dependencies**    | The system relies on Vue.js as the main framework and Vite as the build tool. It also utilizes the Vue Router package for client-side routing.                                                                     |
| **🧩 Modularity**      | The codebase organizes components into separate files, promoting modularity and reusability. The `@` alias is used to access components from the `src` folder, providing easy navigation within the project.          |
| **✔️ Testing**          | The project does not include specific testing frameworks or tools. It could benefit from the implementation of unit tests using libraries like Jest or Cypress for end-to-end testing.                      |
| **⚡️ Performance**      | Since the project is relatively small and focused on front-end functionality, performance appears to be adequate. Further optimization may be required if working with larger data sets or additional features.     |
| **🔐 Security**        | The project lacks explicit security measures, but since it is a client-side app and does not handle sensitive data, security concerns are minimal. Ensure proper data validation and sanitization on the backend. |
| **🔀 Version Control** | The project uses Git for version control, following a standard commit and branch management approach.                                                                                                              |
| **🔌 Integrations**    | The system does not interact with external systems or services directly but has the potential to integrate with backend APIs for data persistence and additional functionality.                                       |
| **📶 Scalability**     | The modular and component-based architecture allows the system to scale easily with the addition of new components or features. It also enables parallel development by different team members.                  |

---


## 📂 Project Structure




---

## 🧩 Modules

<details closed><summary>Root</summary>

| File                                                                                     | Summary                                                                                                                                                                                                                                                                                                                                         |
| ---                                                                                      | ---                                                                                                                                                                                                                                                                                                                                             |
| [index.html](https://github.com/sriparashiva/todo-list-vue/blob/main/index.html)         | This code is an HTML file that sets up the basic structure for a Vite app. It includes a div element with the id "app", which will be the target for rendering the app's content. The script tag at the bottom is used to import and execute the JavaScript code for the app, located in the "main.js" file.                                    |
| [vite.config.js](https://github.com/sriparashiva/todo-list-vue/blob/main/vite.config.js) | This code is a configuration file written in JavaScript for Vite, a modern build tool for web development. It uses the `vite` package and the `vue` plug-in. The code imports functions for resolving file paths and defining the project configuration. It sets an alias for the `@` symbol, which represents the `src` folder of the project. |

</details>

<details closed><summary>Src</summary>

| File                                                                           | Summary                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ---                                                                            | ---                                                                                                                                                                                                                                                                                                                                                                                                                     |
| [App.vue](https://github.com/sriparashiva/todo-list-vue/blob/main/src/App.vue) | The code is for a simple Todo List application. It allows the user to add, remove, and edit todo items. The items can be marked as completed or incomplete, and the list can be filtered to show all tasks, only pending tasks, or only completed tasks. The user can also clear all completed tasks and toggle the completion status of all tasks at once. The code utilizes Vue.js for data binding and UI rendering. |
| [main.js](https://github.com/sriparashiva/todo-list-vue/blob/main/src/main.js) | This code is importing the `createApp` function from the Vue library and the `App` component from a file called App.vue. It then calls `createApp` with the `App` component as an argument and mounts the app to the HTML element with the id "app" on the web page.                                                                                                                                                    |

</details>

---

## 🚀 Getting Started

### ✔️ Prerequisites

Before you begin, ensure that you have the following prerequisites installed:
> - `ℹ️ Requirement 1`
> - `ℹ️ Requirement 2`
> - `ℹ️ ...`

### 📦 Installation

1. Clone the todo-list-vue repository:
```sh
git clone https://github.com/sriparashiva/todo-list-vue
```

2. Change to the project directory:
```sh
cd todo-list-vue
```

3. Install the dependencies:
```sh
npm install
```

### 🎮 Using todo-list-vue

```sh
node app.js
```

### 🧪 Running Tests
```sh
npm test
```

---


## 🗺 Roadmap

> - [X] `ℹ️  Task 1: Implement X`
> - [ ] `ℹ️  Task 2: Refactor Y`
> - [ ] `ℹ️ ...`


---

## 🤝 Contributing

Contributions are always welcome! Please follow these steps:
1. Fork the project repository. This creates a copy of the project on your account that you can modify without affecting the original project.
2. Clone the forked repository to your local machine using a Git client like Git or GitHub Desktop.
3. Create a new branch with a descriptive name (e.g., `new-feature-branch` or `bugfix-issue-123`).
```sh
git checkout -b new-feature-branch
```
4. Make changes to the project's codebase.
5. Commit your changes to your local branch with a clear commit message that explains the changes you've made.
```sh
git commit -m 'Implemented new feature.'
```
6. Push your changes to your forked repository on GitHub using the following command
```sh
git push origin new-feature-branch
```
7. Create a new pull request to the original project repository. In the pull request, describe the changes you've made and why they're necessary.
The project maintainers will review your changes and provide feedback or merge them into the main branch.

---

## 📄 License

This project is licensed under the `ℹ️  INSERT-LICENSE-TYPE` License. See the [LICENSE](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/adding-a-license-to-a-repository) file for additional info.

---

## 👏 Acknowledgments

> - `ℹ️  List any resources, contributors, inspiration, etc.`

---
