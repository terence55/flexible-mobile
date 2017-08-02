# flexible-mobile

## Features

- 用于移动端Web适配
- 基于[lib-flexible](https://github.com/amfe/lib-flexible)修改
- 增加可设置rem基准和最大适配宽度，并将viewport和flexible的设置完全区分

## Installation

```bash
npm install flexible-mobile --save
```
    
## Usage

### 设置rem基准

基准 = 宽度拆分份数 = 设计稿宽度 / 每rem的px

以375的设计稿为例，如最终1rem=12px，则基准= 375 / 12 = 31.25；如1rem=14px，则基准= 375 / 14 = 26.785714286；如1rem=100px，则基准= 375 / 100 = 3.75。
也可在js处设置：window.remscale = 31.25。
原lib-flexible框架固定该值为10，现可根据实际情况自定义设置。

```html
<html>
  <head>
    <meta name="rem-baseline" content="31.25" />
  </head>
  <body>
  </body>
</html>
```

### 自定义viewport

设置viewport，则后续适配都以该viewport的配置为准，不再自适应scale

```html
<html>
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  </head>
  <body>
  </body>
</html>
```

### 自定义initial-dpr

设置initial-dpr，则后续适配都以该dpr为准，不再使用设备自身的dpr

```html
<html>
  <head>
    <meta name="flexible" content="initial-dpr=1" />
  </head>
  <body>
  </body>
</html>
```

### 自定义适配的最大宽度

原lib-flexible框架的自适应宽度最大固定为540，超出此宽度的设备将不再继续放大Root Font Size，现可自定义此宽度值。

```html
<html>
  <head>
    <meta name="flexible" content="initial-dpr=1, max-width=1000" />
  </head>
  <body>
  </body>
</html>
```