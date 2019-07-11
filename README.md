# auto-9-patch-image

## 这是什么

这是一个自动处理九宫格图片的库，类似于 Android 的 .9 图，它能够自动处理，并缩小图片。

其灵感来自于 [onion_ring](https://github.com/kyubuns/onion_ring)，但由于需要直接在前端环境使用，然后就有了当前 2小时的实现。

## Demo

[Demo1](https://raw.githack.com/laoshu133/auto-9-patch-image/master/index.html)

[Demo2](https://raw.githack.com/laoshu133/auto-9-patch-image/master/index.html?url=./examples/2.png)

## 如何使用

### 安装

```
> npm i -S auto-9-patch-image
```

### 引入使用

```javascript
import auto9PatchImage from './src/index.js';

const imageOrUrl = './examples/1.png';

// 同时支持 URL 或者 DOM Image
auto9PatchImage(imageOrUrl).then(ret => {
    console.log(ret); // { image, width, height, offset }

    // 配合 `border-image` 使用更佳，参见 Demo1
    const css = `
        border-image: url(${ret.image}) ${top} ${width - right} ${height - bottom} ${left} fill;
        border-width: ${top}px ${width - right}px ${height - bottom}px ${left}px;
    `;

    domElement.style.cssText = css.trim();
});
```

## License

MIT

