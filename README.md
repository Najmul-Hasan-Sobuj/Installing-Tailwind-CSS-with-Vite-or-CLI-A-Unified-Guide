# Installing TailwindCSS 3 using PostCSS

This guide will take you through the process of setting up a project with TailwindCSS 3 and PostCSS.

## Pre-requisites:
Ensure you have Node.js and npm installed on your machine.

## Steps:

### 1. Initialize a New Project
Initialize a new npm project with the following command:
```bash
npm init -y
```
This command creates a `package.json` file.

### 2. Install Necessary Dependencies
To install TailwindCSS, PostCSS, and Autoprefixer, run the following commands:

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

### 3. Configure Template Paths
To ensure that Tailwind processes your templates and purges unused styles in production, add the paths to all of your template files in your `tailwind.config.js` file:

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### 4. Set Up Stylesheet
First, create a new CSS file inside the `/dist` directory named `main.css`.

Then, add the following Tailwind directives to your `main.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Next, create a new folder named `src` and within that folder, create another folder named `output`.

### 5. Update `package.json` Script
In your `package.json` file, replace the existing `test` script:

```json
"test": "echo \"Error: no test specified\" && exit 1"
```

with the following:

```json
"build": "tailwindcss -i ./dist/main.css -o ./src/output/style.css -w"
```

### 6. Create an HTML File

Inside the `src` folder, create a new file named `index.html` and paste the following code:

```html
<!doctype html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="src/output/style.css" rel="stylesheet">
</head>
<body>
  <h1 class="text-3xl font-bold underline">
    Hello world!
  </h1>
</body>
</html>
```

### 7. Start Development Server

To start the development server and see the changes in real-time, run:

```bash
npm run dev
```

Now, open the `index.html` in a browser, and you should see the styled "Hello World" heading.

---

That's it! You've now set up TailwindCSS 3 with PostCSS. Adjust your templates and styles as needed and enjoy the power and flexibility of TailwindCSS.
