# Trabalhando com Webpack

## Projeto base para Webpack

Passos para montar do zero:

```
$ mkdir webpack-hello-world
$ cd webpack-hello-world
$ npm init
$ npm install webpack webpack-dev-server css-loader style-loader --save-dev
$ touch style.css
```

```
-- style.css
body {
    background: blue;
}
```

```
$ touch index.js
```

```
-- index.js
require("./style.css");
document.write("Hello World Workpack!!!");
```

```
$ touch index.html
```

```
-- index.html
<html>
    <head>
        <meta charset="utf-8">
    </head>
    <body>
        <script type="text/javascript" src="bundle.js" charset="utf-8"></script>
    </body>
</html>
```

```
$ touch webpack.config.js
```

```
-- webpack.config.js
module.exports = {
    entry: "./index.js",
    output: {
        path: __dirname,
        filename: "bundle.js"
    },
    module: {
        loaders: [
            { test: /\.css$/, loader: "style!css" }
        ]
    }
};
```

```
$ npm run dev
```
