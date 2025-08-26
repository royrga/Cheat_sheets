---
tags:
  - JavaScript
  - TypeSrcript
  - Framework
  - ReactNative
---

# ESLint

ESLint is a static code analysis tool for identifying and fixing problems in JavaScript code. It helps enforce consistent coding styles, catch potential bugs, and improve code quality. In React Native projects, ESLint is commonly used alongside plugins and configurations tailored for React, React Native, and TypeScript to ensure best practices and maintainable code.

## Table of Contents

- [Installation](#installation)  
- [Configuration](#configuration)  
- [Usage](#usage)  

## Installation

1. **Install ESLint and Required Plugins**  
    Run the following command to install ESLint and necessary plugins for React Native and TypeScript:  
    ```bash
    npm install --save-dev eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint-plugin-react eslint-plugin-react-native eslint-plugin-import eslint-plugin-jsx-a11y
    ```

2. **Install ESLint Configurations**  
    Optionally, you can use a popular ESLint configuration like Airbnb:  
    ```bash
    npx install-peerdeps --dev eslint-config-airbnb
    ```

3. **Install Prettier (Optional)**  
    If you want to integrate Prettier for code formatting:  
    ```bash
    npm install --save-dev prettier eslint-config-prettier eslint-plugin-prettier
    ```

---

## Configuration

1. **Create an ESLint Configuration File**  
    Generate an ESLint configuration file:  
    ```bash
    npx eslint --init
    ```

    Choose the following options during setup:
    - **How would you like to use ESLint?**: To check syntax, find problems, and enforce code style.
    - **What type of modules does your project use?**: JavaScript modules (import/export).
    - **Which framework does your project use?**: React.
    - **Does your project use TypeScript?**: Yes.
    - **Where does your code run?**: React Native.
    - **What format do you want your config file to be in?**: JSON.

2. **Modify `.eslintrc.json`**  
    Update the configuration file to include TypeScript and React Native-specific rules:  
    ```json
    {
      "parser": "@typescript-eslint/parser",
      "extends": [
         "eslint:recommended",
         "plugin:react/recommended",
         "plugin:react-native/all",
         "plugin:@typescript-eslint/recommended",
         "plugin:prettier/recommended"
      ],
      "plugins": ["react", "react-native", "@typescript-eslint"],
      "env": {
         "react-native/react-native": true
      },
      "settings": {
         "react": {
            "version": "detect"
         }
      },
      "rules": {
         // Add custom rules here
      }
    }
    ```

3. **Add `.eslintignore`**  
    Create a `.eslintignore` file to exclude certain files or directories:  
    ```
    node_modules/
    build/
    dist/
    ```

---

## Usage

1. **Run ESLint**  
    Use the following command to lint your project:  
    ```bash
    npx eslint . --ext .js,.jsx,.ts,.tsx
    ```

2. **Fix Issues Automatically**  
    Run ESLint with the `--fix` flag to automatically fix issues:  
    ```bash
    npx eslint . --ext .js,.jsx,.ts,.tsx --fix
    ```

3. **Integrate with Your Editor**  
    Install an ESLint plugin for your code editor (e.g., VS Code) to get real-time linting feedback.

4. **Add a Script to `package.json`**  
    Add a script to simplify running ESLint:  
    ```json
    "scripts": {
      "lint": "eslint . --ext .js,.jsx,.ts,.tsx"
    }
    ```

Now you can run `npm run lint` to lint your project.
