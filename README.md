# test-react-vite

Creating from scracth

## Create Project
```sh
npm create vite@latest app -- --template react
cd app
```
This command creates a new Vite project using the React template.

### Install dependencies
```sh
npm install -g gh-pages
```
Install the ;gh-pages; package to enable GitHub Pages deployment and other dependencies if not already installed.

### Create `npm` scripts
Add the following scripts into the `package.json` file:
```json
    "build:dev": "vite build --mode development",
    "build:prd": "vite build --mode production",

    "deploy:dev": "npm run build:dev && npx serve dist",
    "deploy:git": "npm run build:prd && gh-pages -d dist"
```

### Configure Deployment Mode (Development/Production)
Add `mode` param and `base` config into the `vite.config.js` file:
```js
export default defineConfig(({ mode }) => ({
  base: mode === "production" ? "/test-react-vite/" : "/",
  plugins: [react()],
}));
```

## Development Environment
### Deploy Locally to Test
```sh
npm run deploy:dev
```

## Production Environment
### Deploy on GitHub as Production
``` sh
npm run deploy:git
```

### Access at GitHub
Access your deployed site at:
`https://<your-github-username>.github.io/<repository-name>`

> Example URL: `https://dmyan.github.io/test-react-vite/`
