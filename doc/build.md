## Building

If you need to use this module outside a CommonJS environment, you can build a standalone UMD module as follows:

```

npm install -g uglify-js
npm install -g browserify

$ browserify index.js --standalone Espresso | uglifyjs > node-mini-obj.min.js
```