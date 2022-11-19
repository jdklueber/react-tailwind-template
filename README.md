# React plus Tailwind Template
This repository contains an empty "hello world" React application for use as a template repo for spinning up new react applications with Tailwindcss already set up.  To use it:
1.  Create a new repository with this as a template
1.  Inside of your terminal, run `npm install`

The application should be runnable at this point, and contains only the bare bones necessary to display Hello World styled with Tailwindcss.

Here are the steps used to create this template repo:

### Build a new React application

From your usual project directory:

```console
npx create-react-app <application name>
```

## Remove unnecessary files

* From `public/`:  Remove all but index.html
* Inside of `index.html`: Remove all references to `favicon.ico`, `logo.png`, `manifest.json`.  Also consider changing the `title` tag and the `meta` `description` tag.
* From `src`: Remove all but `App.js`, `index.css`, and `index.js`. 
* `App.js`:  Replace with the following snippet

```javascript
function App() {
  return (
    <div>
      Hello World
    </div>
  );
}

export default App;

```

* `index.css`:  Delete all content
* `index.js`:  Delete references to `reportWebVitals`
* `package.json`:  Change the name of the project if needed, remove reference to `web-vitals` in the dependencies section.

Run the project to verify you get a Hello World message.

## Install Tailwindcss

See https://tailwindcss.com/docs/installation/framework-guides for other frameworks.

#### Install tailwind

From the console:

```console
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

#### Configure tailwind

Update `tailwind.config.js`

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

#### Update `index.css`

Add this to `index.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

#### Restart the server and verify that tailwind styling is in place

Update `App.js` to look like this:

```javascript
function App() {
  return (
    <div className="text-4xl">
      Hello World
    </div>
  );
}

export default App;

```

Your hello world should now be quite large and sans-serif.

## Making a new favicon.ico file: 

See https://favicon.io/favicon-generator/

If you do this, you'll probably want to add the favicon link inside of `index.html`.

```html
  <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
```

