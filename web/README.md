
### Create Vite React Application

```bash
yarn create vite
```

### Add ESLint

Follow the instructions in [this blog](https://www.robinwieruch.de/vite-eslint/)

```bash
yarn add eslint-plugin-vue
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
yarn add eslint eslint-config-react-app
```