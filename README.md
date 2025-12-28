# vue-lesson-16

## What I Learned

### Vue CLI Project Structure

```
vue-lesson-16/
├── public/              # Static assets
│   └── index.html       # HTML template with <div id="app">
├── src/
│   ├── main.js          # Entry point (createApp, mount)
│   ├── App.vue          # Root component
│   └── components/      # Vue components
├── babel.config.js      # Babel configuration
└── package.json
```

**Running the project:**
```bash
npm run serve   # Development server
npm run build   # Production build
npm run lint    # ESLint
```

### Props Naming Convention: camelCase vs kebab-case

Vue automatically converts between HTML attribute naming (kebab-case) and JavaScript property naming (camelCase):

**In component definition (JavaScript - camelCase):**
```javascript
props: ['name', 'phoneNumber', 'emailAdress']
```

**In template usage (HTML - kebab-case):**
```vue
<friend-contact
  name="Rikuto Mikado"
  phone-number="0123-45678-90"
  email-adress="rikuto@example.com"
></friend-contact>
```

**Why the difference?**
- HTML attributes are case-insensitive, so `phoneNumber` and `phonenumber` would be treated the same
- JavaScript uses camelCase convention for property names
- Vue automatically converts: `phone-number` (template) → `phoneNumber` (props)

**Props definition syntax:**
```javascript
// Array syntax: Simple, no validation
props: ['name', 'phoneNumber', 'emailAdress']

// Object syntax: Type checking (recommended for production)
props: {
  name: String,
  phoneNumber: String,
  emailAdress: String
}
```

### Dynamic Template Expressions

Use ternary operators for simple conditional rendering:

```vue
<button @click="toggleDetails">
  {{ detailsVisible ? 'Hide' : 'Show' }} Details
</button>
```

For complex logic, use computed properties instead.

## Q&A

**Q: Why does Vue convert between camelCase and kebab-case?**
A: HTML attributes are case-insensitive, while JavaScript uses camelCase convention. Vue bridges this gap automatically.

**Q: Array vs Object syntax for props?**
A: Array syntax is simpler for quick prototyping. Object syntax provides type validation and is recommended for production code.

**Q: When to use ternary operators vs computed properties?**
A: Ternary operators are fine for simple conditions (1-2 variables). Use computed properties for complex logic or reusable calculations.

## Challenges

### Vue CLI vs Vite

| Aspect | Vue CLI | Vite |
|--------|---------|------|
| **Build tool** | Webpack | Rollup + esbuild |
| **Dev server** | Slower | Faster (ESM) |
| **Config** | `vue.config.js` | `vite.config.js` |
| **Browser support** | Better legacy support | Modern browsers |

Vue CLI requires more configuration files (babel.config.js, jsconfig.json, vue.config.js) because it uses Webpack under the hood.

## Memo

This lesson enhanced the FriendContact component by implementing dynamic button text using ternary operators in template interpolation, allowing the button caption to toggle between "Show Details" and "Hide Details" based on component state. Additionally, we learned Vue's automatic naming convention conversion between kebab-case (HTML templates) and camelCase (JavaScript props), which bridges the gap between HTML's case-insensitive attributes and JavaScript's camelCase convention. Props can be defined using either array syntax for simplicity or object syntax for type validation in production environments.
