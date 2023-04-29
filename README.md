# Webpack Resources

這份文檔整理了常用的 webpack loader, asset/resource, parser，將資源文件轉換成 webpack 模組。

---

### 載入 js / json

- 無須任何配置

### 載入 css

- npm 依賴

```bash
npm install -D style-loader css-loader
```

- webpack.config.js

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.css$/i,
        use: ["style-loader", "css-loader"],
      },
    ],
  },
};
```

### 載入 sass / scss

- npm 依賴

```bash
npm install -D style-loader css-loader sass-loader
```

- webpack.config.js

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.s[ac]ss$/i,
        use: ["style-loader", "css-loader", "sass-loader"],
      },
    ],
  },
};
```

### 載入 less

- npm 依賴

```bash
npm install -D style-loader css-loader less-loader
```

- webpack.config.js

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.less$/i,
        use: ["style-loader", "css-loader", "less-loader"],
      },
    ],
  },
};
```

### 載入 images

- webpack.config.js

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.(png|svg|jpg|jpeg|gif)$/i,
        type: "asset/resource",
      },
    ],
  },
};
```

### 載入 fonts

- webpack.config.js

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.(woff|woff2|eot|ttf|otf)$/i,
        type: "asset/resource",
      },
    ],
  },
};
```

### 載入 csv / tsv / xml

- npm 依賴

```bash
npm install -D csv-loader xml-loader
```

- webpack.config.js

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.(csv|tsv)$/i,
        use: ["csv-loader"],
      },
      {
        test: /\.xml$/i,
        use: ["xml-loader"],
      },
    ],
  },
};
```

### 載入 toml

- npm 依賴

```bash
npm install toml -D
```

- webpack.config.js

```js
const toml = require("toml");
module.exports = {
  module: {
    rules: [
      {
        test: /\.toml$/i,
        type: "json",
        parser: {
          parse: toml.parse,
        },
      },
    ],
  },
};
```

### 載入 yaml

- npm 依賴

```bash
npm install yamljs -D
```

- webpack.config.js

```js
const yaml = require("yamljs");
module.exports = {
  module: {
    rules: [
      {
        test: /\.yaml$/i,
        type: "json",
        parser: {
          parse: yaml.parse,
        },
      },
    ],
  },
};
```

### 載入 json5

- npm 依賴

```bash
npm install toml -D
```

- webpack.config.js

```js
const json5 = require("json5");
module.exports = {
  module: {
    rules: [
      {
        test: /\.json5$/i,
        type: "json",
        parser: {
          parse: json5.parse,
        },
      },
    ],
  },
};
```
