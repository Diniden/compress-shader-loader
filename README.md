# Compress Shader Loader

This loader was designed to aid in development with the DeltaV framework. It
allows for shader code and fragments to be written into separate files and then
inlined into the bundle for your project.

## Installation and Use

To install simply:

```sh
npm install compress-shader-loader
```

This example will load .fs and .vs files and inline their contents into your bundle:

```json
{
  "modules": {
    "rules": [
      { "test": /\.[fv]s$/, "use": ["shader-compress-loader"] },
    ]
  }
}
```

## Recommendations

I would recommend using `raw-loader` to inline your shader files in development mode
and use this loader for production. Something like this:

```javascript
...
  { test: /\.[fv]s$/, use: IS_PRODUCTION ? ['shader-compress-loader'] : ['raw-loader'] },
...
```

This will help you have a MUCH more useful debugging experience.
