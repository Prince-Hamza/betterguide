After a long research MetroJS bundler default not compile typescript .ts and .tsx extension files. We need tell MetroJS bundler to compile .ts and .tsx files i solved this error by edit metro.config.js file in root project folder by following.

Edited on September 2022

Added cjx and json extensions to below snippet
All extensions listed below not required it's depend on what language you choose javascript or typescript, and your dependencies


```
module.exports = {
  transformer: {
    getTransformOptions: async () => ({
      transform: {
        experimentalImportSupport: false,
        inlineRequires: false,
      },
    }),
  },
  resolver: {
    sourceExts: ['jsx', 'js', 'ts', 'tsx', 'cjs', 'json'] //add here
  },
};
```
