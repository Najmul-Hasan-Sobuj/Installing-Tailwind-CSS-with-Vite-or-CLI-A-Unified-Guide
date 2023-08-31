# Installing Tailwind CSS with Vite or CLI: A Unified Guide

This guide aims to simplify the process of installing Tailwind CSS in a project, providing options for both Vite or CLI. Tailwind CSS is a utility-first CSS framework, while Vite is a fast build tool optimized for development experience. 

## Table of Contents
1. [Prerequisites](#prerequisites)
2. [Initialize a New Project](#initialize-a-new-project)
3. [Install Necessary Dependencies](#install-necessary-dependencies)
4. [Configure Tailwind](#configure-tailwind)
5. [Set Up Stylesheet](#set-up-stylesheet)
6. [Run the Development Server](#run-the-development-server)
7. [Create an HTML File](#create-an-html-file)
8. [Appendix](#appendix)

---

## Prerequisites

- Node.js and npm installed on your machine
- Basic understanding of JavaScript, HTML, and CSS
- Access to a terminal or command-line interface

## Initialize a New Project

**Vite Option**
1. Open your terminal and navigate to the directory where you want to create a new project.
2. Run the following command:
```bash
npm create vite@latest
```
3. Choose your project name, template as `Vanilla`, and language as `JavaScript`.

**CLI Option**
1. Open the terminal and navigate to your desired directory.
2. Run the command:
```bash
npm init -y
```

## Install Necessary Dependencies

**Vite Option**
1. Navigate to your project folder and install dependencies:
```bash
cd your-project-name
npm install
```

**CLI Option**
1. Navigate to your project folder. 

**Common Step for Both**
2. Install Tailwind CSS, and Autoprefixer:
```bash
npm install -D tailwindcss
```

## Configure Tailwind

1. Initialize Tailwind:
```bash
npx tailwindcss init
```
2. Edit `tailwind.config.js` as follows:
```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

## Set Up Stylesheet

**Vite Option**
1. Update your stylesheet (`style.css`) with the following:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

**CLI Option**
1. Create a new CSS file in the `/dist` directory, named `main.css`.
2. Add the following to `main.css`:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## Run the Development Server

**Vite Option**
```bash
npm run dev
```

**CLI Option**
1. Update your `package.json` script:
```json
"build": "tailwindcss -i ./dist/main.css -o ./src/output/style.css -w"
```
2. Run the build script:
```bash
npm run build
```

## Create an HTML File for CLI

Create and style an `index.html` file for either option. Make sure to link the stylesheet generated by Tailwind.

**Example HTML**
```html
<!doctype html>
<html>

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="output/style.css" rel="stylesheet">
</head>

<body>
    <h1 class="text-3xl font-bold underline">
        Hello world!
    </h1>
</body>

</html>
```

## HTML File for Vite

**Example HTML**
```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <link rel="icon" type="image/svg+xml" href="/vite.svg" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Vite App</title>
</head>
<body>
  <!-- Your Tailwind-enabled HTML goes here -->
  <!-- <div id="app"></div> -->
  <script type="module" src="/main.js"></script>
</body>
</html>
```
## Appendix

- [Vite Official Documentation](https://vitejs.dev/guide/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)

---

By following these steps, you can install Tailwind CSS either with Vite or CLI according to your project's needs.
