# vue-lesson-16

## What I Learned

### Vue CLI Project Structure

First time using Vue CLI. The file structure differs from typical Vite projects:

```
vue-lesson-16/
├── public/              # Static assets (served as-is)
│   ├── favicon.ico
│   └── index.html       # HTML template with <div id="app">
├── src/
│   ├── main.js          # Entry point (createApp, mount)
│   ├── App.vue          # Root component
│   └── components/      # Vue components
├── babel.config.js      # Babel configuration
├── jsconfig.json        # JS project config
├── vue.config.js        # Vue CLI config
└── package.json
```

**Key differences from basic setup:**
- `public/index.html` serves as template (not in root)
- `src/main.js` is the entry point
- Configuration files: babel, jsconfig, vue.config
- CLI handles webpack config internally

**Running the project:**
```bash
npm run serve   # Development server
npm run build   # Production build
npm run lint    # ESLint
```

## Challenges

### Vue CLI vs Vite

| Aspect | Vue CLI | Vite |
|--------|---------|------|
| **Build tool** | Webpack | Rollup + esbuild |
| **Dev server start** | Slower (bundles everything) | Faster (ESM, on-demand) |
| **HMR speed** | Slower | Faster |
| **Config** | `vue.config.js` (webpack-based) | `vite.config.js` (simpler) |
| **Browser support** | Better legacy support (Babel) | Modern browsers (ES6+) |
| **Maturity** | Older, stable, more plugins | Newer, less ecosystem |
| **File structure** | More config files | Simpler structure |

**Main challenge:**
Understanding why Vue CLI needs more configuration files (babel.config.js, jsconfig.json, vue.config.js) compared to Vite's single config file. This is because Vue CLI uses Webpack under the hood, which requires more setup for transpilation and bundling.

## Notes

