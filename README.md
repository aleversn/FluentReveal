# Fluent Reveal
Provide the Reveal effects based on the Fluent Design System.

## 中文
基于 [FluentRevealEffect](https://github.com/d2phap/fluent-reveal-effect)

在原作者基础上本项目做出以下改进:

1. 本项目提供两种`Reveal`版本, 一种是基于背景元素遮罩的(原作者版本), 另一种是基于元素自身的反射. 基于背景元素遮罩的效果在整个组件半透明状态时无法体现`Reveal Border`的效果. 基于元素自身反射的版本支持透明背景的`Reveal Border`, 但是无法实现圆角状态的显示.
2. 本项目定义了全局的元素回收器和`Reveal`效果触发阈值, 有效地降低了性能损耗, 通过及时的回收元素避免了元素过多导致的卡顿问题.
3. 本项目提供的`Click Wave`效果在原版本基础上增加了点击时的涟漪效果, 更贴近`Windows 10 UWP`原生的`Reveal`效果.
4. 应用效果时支持元素以`选择器`形式或`变量`形式被指定.

### 使用方法

使用前假设您当前的开发环境已满足`ES6`的支持, 若不满足请用户自行将`class`写法转换为函数形式.

1. RevealMasked.js

引入`RevealEffectsMasked`

```javascript
import { RevealEffectsMasked } from './Js/revealMasked';
```

HTML要求

```html
<div id="#sample">
  <div class="border-container">
    <div class="element-container"></div>
  </div>
</div>
```
要求产生反射效果的元素外层包裹一层背景层`border-container`, 背景层与元素层之间应有一定间隔, 这个间隔即为`Reveal-Border`的边框宽度.

应用效果

```javascript
let FR = new RevealEffectsMasked("body", {
    selector: document.getElementById('#sample').querySelectorAll('.border-container')[0], //推荐写法, 或`#sample .border-container`也可以
    backgroundGradientSize: 150,
    borderGradientSize: 80,
    borderLightColor: "rgba(255, 255, 255, 0.25)",
    backgroundLightColor: "rgba(255, 255, 255, 0.25)",
    childrenSelector: document.getElementById('#sample').querySelectorAll('.element-container')[0]  //推荐写法, 或`#sample .element-container`也可以
});
```

2. RevealDirect.js

引入`RevealEffects`

```javascript
import { RevealEffects } from './Js/revealDirect';
```

HTML要求

```html
<div id="#sample">
  <div class="element-container"></div>
</div>
```

应用效果

```javascript
let FR = new RevealEffects("body", {
    selector: document.getElementById('#sample').querySelectorAll('.border-container')[0], //推荐写法, 或`#sample .border-container`也可以
    backgroundGradientSize: 150,
    borderGradientSize: 80,
    borderLightColor: "rgba(255, 255, 255, 0.25)",
    backgroundLightColor: "rgba(255, 255, 255, 0.25)"
});
```

## English

Based on [FluentRevealEffect](https://github.com/d2phap/fluent-reveal-effect)

There are some improvements made to this project on the basis of the original author:

1. 本项目提供两种`Reveal`版本, 一种是基于背景元素遮罩的(原作者版本), 另一种是基于元素自身的反射. 基于背景元素遮罩的效果在整个组件半透明状态时无法体现`Reveal Border`的效果. 基于元素自身反射的版本支持透明背景的`Reveal Border`, 但是无法实现圆角状态的显示.
2. 本项目定义了全局的元素回收器和`Reveal`效果触发阈值, 有效地降低了性能损耗, 通过及时的回收元素避免了元素过多导致的卡顿问题.
3. 本项目提供的`Click Wave`效果在原版本基础上增加了点击时的涟漪效果, 更贴近`Windows 10 UWP`原生的`Reveal`效果.
4. 应用效果时支持元素以`选择器`形式或`变量`形式被指定.

1. This project offers two 'Reveal' versions, one is based on the background element mask (the original author version) and the other based on the reflection of the element itself. The background element-based matte effect does not reflect the effect of `Reveal Border` when the entire component is translucent. Versions based on the reflection of the element itself support `Reveal Border` with a transparent background, but cannot be displayed in `border-radius` status.
2. This project defines the global element recycler and `Reveal` effect trigger threshold, effectively reducing performance loss, avoiding the Caton problem caused by excessive elements by recycling elements in a timely manner.
3. The `Click Wave` effect provided by this project adds a click-to-click effect on top of the original version, which is closer to the `Reveal` effects of the `Windows 10 UWP` native.
4. When applying an effect, the support element is specified in the form of a `selector` or a `variable`.

### Usage

Suppose your current development environment has supported `ES6`, if not, please convert the `class` writing method into `function` form on your own.

1. RevealMasked.js

Import `RevealEffectsMasked`

```javascript
import { RevealEffectsMasked } from './Js/revealMasked';
```

HTML Requests

```html
<div id="#sample">
  <div class="border-container">
    <div class="element-container"></div>
  </div>
</div>
```
The outer layer of the element that produces the reflection is wrapped in a background layer `border-container`, and there should be a certain interval between the background layer and the element layer, which is the border width of `Reveal-Border`.

Apply Effects

```javascript
let FR = new RevealEffectsMasked("body", {
    selector: document.getElementById('#sample').querySelectorAll('.border-container')[0], //Recommended, or `#sample .border-container`
    backgroundGradientSize: 150,
    borderGradientSize: 80,
    borderLightColor: "rgba(255, 255, 255, 0.25)",
    backgroundLightColor: "rgba(255, 255, 255, 0.25)",
    childrenSelector: document.getElementById('#sample').querySelectorAll('.element-container')[0]  //Recommended, or`#sample .element-container`
});
```

2. RevealDirect.js

Import `RevealEffects`

```javascript
import { RevealEffects } from './Js/revealDirect';
```

HTML Requests

```html
<div id="#sample">
  <div class="element-container"></div>
</div>
```

Apply Effects

```javascript
let FR = new RevealEffects("body", {
    selector: document.getElementById('#sample').querySelectorAll('.border-container')[0], //Recommended, or `#sample .border-container`
    backgroundGradientSize: 150,
    borderGradientSize: 80,
    borderLightColor: "rgba(255, 255, 255, 0.25)",
    backgroundLightColor: "rgba(255, 255, 255, 0.25)"
});
```

## Demo

- Masked [Here](https://aleversn.github.io/VFluent/zh/Button/)
- Direct [Here](https://aleversn.github.io/VFluent/zh/ListView/)
