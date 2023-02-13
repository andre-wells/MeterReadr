
### Create Vite React Application

```bash
yarn create vite
```

### Add ESLint

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