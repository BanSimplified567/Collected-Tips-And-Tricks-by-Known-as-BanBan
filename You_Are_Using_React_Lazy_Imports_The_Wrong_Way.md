# You Are Using React Lazy Imports the Wrong Way

## #javascript #webdev #programming #react

### React.js (6 Part Series)

1. [Deploy React.js application using AWS S3 & GitLab pipelines for automatic deployment 2024](#)
2. [How I optimized loading time using service workers in frontend](#)
...
5. **You Are Using React Lazy Imports the Wrong Way**
6. [Don't use React imports like this. Use Wrapper Pattern instead](#)

---

# I saw today in a project lazy imports like this

```javascript
const AnimatedScore = React.lazy(() => import('../components/AnimatedScore'))
const FireworksCanvas = React.lazy(() => import('../components/FireworksCanvas'))
const Header = React.lazy(() => import('../components/Header'))
const URLForm = React.lazy(() => import('../components/URLForm'))
const LoadingErrorMessages = React.lazy(() => import('../components/LoadingErrorMessages'))
const RadarChartSection = React.lazy(() => import('../components/RadarChartSection'))
const ExceededSentences = React.lazy(() => import('../components/ExceededSentences'))
const Footer = React.lazy(() => import('../components/Footer'))
const SubHeader = React.lazy(() => import('../components/SubHeader'))
```

## After running npm run build, the build time took 3.64 seconds

## So, what did I do to optimize this? I switched to using the map method

```js
const [
  AnimatedScore,
  FireworksCanvas,
  Header,
  URLForm,
  LoadingErrorMessages,
  RadarChartSection,
  ExceededSentences,
  Footer,
  SubHeader,
] = [
  'AnimatedScore',
  'FireworksCanvas',
  'Header',
  'URLForm',
  'LoadingErrorMessages',
  'RadarChartSection',
  'ExceededSentences',
  'Footer',
  'SubHeader',
].map((component) => React.lazy(() => import(`../components/${component}.tsx`)))

// And after this modification, the build time dropped to 926ms. Incredible, isn't it? 🚀

```

## Explanation

## For those unfamiliar with chunks, here’s a quick rundown

 Chunks are pieces of JavaScript code that a bundler (like Vite or Webpack) splits to optimize loading. Instead of loading one large file, the browser loads only the necessary chunks as needed

### For example, if your app has three pages—Home, About, and Contact—a single bundle would force users to download everything, even if they never visit all pages

Instead, a bundler splits your code into optimized chunks

- main.js → Shared code used across the entire app.
- home-[hash].js → Loaded only when the user visits the Home page.
- about-[hash].js → Loaded only when the user visits the About page.
- Bundlers often add a unique hash (e.g., home-abc123.js) for better caching and cache invalidation.

## Why Does the map Method Optimize Build Time?

### By using .map() for dynamic imports, the bundler can group and optimize chunks more efficiently, instead of handling each import() separately

## This allows the bundler (like Vite) to

- Process imports in one go, improving efficiency.
- Reduce redundant operations in the bundling process.
- Enable better chunk creation and grouping.
- Parallelize chunk creation, leading to faster builds.

# Summary

### Switching from single-line lazy imports to using a map for dynamic imports improves performance by

✅ Reducing redundant bundler operations
✅ Creating optimized chunks
✅ Enhancing parallelization for faster builds
✅ Improving chunk reuse and efficiency

- Try this approach and watch your build times drop significantly! 🚀

- This Markdown version maintains the structure and formatting while making it easier to read and navigate. 🚀 Let me know if you need any tweaks!
