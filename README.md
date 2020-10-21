# Tailwind-setup
Basic setup of tailwind required for react like application.

## Create a React environment first
`npx create-react-app myapp , cd myapp`

## Install Tailwind, Postcss and Autoprefixer via npm 
#### ( -D is  '-g-dev' dev dependency, Postcss is to compile tailwindcss and allow autoprefixer plugin, autoprefixer is for rendering prefixes)

`npm i -D tailwindcss postcss-cli autoprefixer@9.8.6 --save`

## Generate Tailwind.config.js file
`npx tailwind init -full'

## Create a 'postcss.config.js' file and insert below code in it 
```jsx
const tailwindcss = require("tailwindcss");

module.exports = {
  plugins: [tailwindcss("./tailwind.config.js"), require("autoprefixer")],
};
```
## Inside folder 'scr', Create a folder named 'assets' add add two css files inside it (SRC > ASSETS >)
* main.css
* tailwind.css

#### Inside tailwind.css inject below styles
```jsx
@import "tailwindcss/base";

@import "tailwindcss/components";

@import "tailwindcss/utilities";
```
## In 'package.json', inject below code inside 'scripts'
```json
"scripts": {
  "start": "npm run watch:css && react-scripts start",
  "build": "npm run build:css && react-scripts build",
  "build:css": "postcss src/assets/tailwind.css -o src/assets/main.css",
  "watch:css": "postcss src/assets/tailwind.css -o src/assets/main.css"
 }
```
## Inside 'index.js' file
`import './assets/main.css' `

# Important
` npm run`
