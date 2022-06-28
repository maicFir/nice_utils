# nice_utils

一个好用的工具类库

### 项目简介

从 0 到 1 配合`ts`使用`webpack5`搭建一个通用的组件库，支持`ts`编写工具函数，收集一些项目好用的工具函数

### 项目使用技术栈

- 🔥 `webpack5`、`typescript`、`babel`、...

### 项目目录

```js
|----config  // webpack打包相关配置文件
       |---webpack.common.ts // webpack 公用配置
       |---webpack.dev.ts // webpack 开发环境配置
       |---webpack.prod.ts // webpack 生产环境配置
       |---webpack.target.ts // 打包umd,cjs,esm模式的代码
|----example  // 测试代码
|----src  // 源码入口
|     |---index.ts // 源码入口文件
|     |---formateUrl.ts // 格式化url
|     |---....
|     type
|-----package.json // 安装依赖包必须的文件
|-----tsconfig.json // ts环境相关的配置
|-----webpack.config.ts // webpack打包的入口文件
```

### 环境安装

依赖`nodejs`,先下载对应 node,我的 node 版本是`v14.17.0`,由于使用最新`webpack5`,建议安装比较新的`node`版本，不然可能会存在兼容性问题,下载[node](https://registry.npmmirror.com/binary.html?path=node/)参考官方地址

### 快速开始

1、 git clone `https://github.com/maicFir/nice_utils.git`

2、 cd `nice_utils`

3、 npm i

### 启动本地服务

执行以下命令

```js
 npm run start
```

打开谷歌地址`http://localhost:8080`,mac(option + command +i)打开开发者模拟器，选择不同设备进行查阅页面，window(右键审查/f12 选择模拟器)打开页面访问

在`src`中新增对应工具函数，然后测试其效果

```js
// example/index.ts
import * as nice_utils from '../src/index';
console.log(nice_utils);
console.log('formateUrl:', nice_utils.formateUrl('http://www.example.com?name=Maic&age=18'));
console.log('hasOwn:', nice_utils.hasOwn({ publictext: 'Web技术学苑' }, 'publictext'));
console.log('isType:', nice_utils.isType('Web技术学苑')('String'));
```

### 打包输出最终`dist`文件

```js
npm run build
```

在根目录下生成`dist`

![](https://files.mdnice.com/user/24614/47df5bff-313d-430a-822a-3b727bd92093.png)

### API

`formateUrl`

```js
const nice_utils = require('@maicfir/nice_utils');
// 使用示例
nice_utils.formateUrl('http://www.example.com?name=Maic&age=18'); // {name: 'Maic',age: 18}
```

`getOrigin`

```js
const nice_utils = require('@maicfir/nice_utils');
nice_utils.getOrigin(); // 获取当前访问的域名
```

`hasOwn`

```js
const nice_utils = require('@maicfir/nice_utils');
nice_utils.hasOwn({ name: '张三' }, 'name'); // true name 是不是在对象中
```

`isType`

```js
const nice_utils = require('@maicfir/nice_utils');
nice_utils.isType('')('String'); // true 判断是不是字符串类型
```

`lazyFunction`

```js
const nice_utils = require('@maicfir/nice_utils');
const fn = nice_utils.lazyFunction(() => require('../xxx/index.js')); //函数懒加载
```

`memorize`

```js
const { memorize } = require('@maicfir/nice_utils');
const fn = memorize(() => console.log(111));
```

`mergeDeep`

```js
const { mergeDeep } = require('@maicfir/nice_utils');
mergeDeep({}, { a: 1, b: 2, info: { a: 1, b: 1 } });
```

`timerChunk`

```js
const { timerChunk } = require('@maicfir/nice_utils');
const fn = timerChunk([], (res) => {
  console.log(res);
});
const ret = fn();
console.log(ret);
```

### About me

[![GitHub Pages](https://github.com/element-plus/element-plus-playground/actions/workflows/gh-pages.yml/badge.svg)](https://github.com/maicFir/lessonNote)

- 看完项目如果觉得对你有帮助，就点个`star`鼓励下作者哈

- 更多技术关注`公众号:Web技术学苑`，好好学习、天天向上!

![](https://files.mdnice.com/user/24614/50dd18f5-e2d5-4eb5-ac76-716aec6da88f.jpg)

### License

[MIT](./LICENSE) License © 2022-PRESENT [maicFir](https://github.com/maicFir)
