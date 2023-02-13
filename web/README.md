
### Create Vite React Application

```bash
yarn create vite
```


### Add ESLint to project

https://dev.to/knowankit/setup-eslint-and-prettier-in-react-app-357b


```bash
yarn add eslint --dev
yarn run eslint --init
```

Configure settings using the prompts.

```bash
yarn run v1.22.19
$ /home/andrew/100days/MeterReadr/web/node_modules/.bin/eslint --init
You can also run this command directly using 'npm init @eslint/config'.
✔ How would you like to use ESLint? · style
✔ What type of modules does your project use? · esm
✔ Which framework does your project use? · react
✔ Does your project use TypeScript? · No / Yes
✔ Where does your code run? · browser
✔ How would you like to define a style for your project? · guide
✔ Which style guide do you want to follow? · standard-with-typescript
✔ What format do you want your config file to be in? · JavaScript
Checking peerDependencies of eslint-config-standard-with-typescript@latest
The config that youve selected requires the following dependencies:

eslint-plugin-react@latest eslint-config-standard-with-typescript@latest @typescript-eslint/eslint-plugin@^5.0.0 eslint@^8.0.1 eslint-plugin-import@^2.25.2 eslint-plugin-n@^15.0.0 eslint-plugin-promise@^6.0.0 typescript@*
✔ Would you like to install them now? · No / Yes
✔ Which package manager do you want to use? · yarn
```


### Update Vite to use ESLint

Follow the instructions in [this blog](https://www.robinwieruch.de/vite-eslint/)

```bash
yarn add vite-plugin-eslint
```

Update `vite.config.ts` with the following

```typescript
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';
import eslint from 'vite-plugin-eslint';

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react(), eslint()],
});
```

Now Vite knows about ESLint, but we do not have the actual ESLint dependency installed yet.

```
yarn add eslint eslint-config-react-app prettier eslint-plugin-prettier prettier
```

Next we need to add an ESLint config file `.eslintrc.js`

- We want to use a JS file, so remove the `"type": "module"` from `package.json 
- Create the basic `.eslintrc.js` file

```js
module.exports = {
    extends: [
        'react-app'
    ]
}
```