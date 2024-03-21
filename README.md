将 Tailwind CSS 作为 PostCSS 插件安装是将其与构建工具（如 webpack、Rollup、Vite 和 Parcel）集成的最无缝方式。

1、
安装 Tailwind CSS
通过 npm 安装 tailwindcss 及其对等依赖项，并创建你的 tailwind.config.js 文件。

Terminal

npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p

2、
将 Tailwind 添加到你的 PostCSS 配置中
将 tailwindcss 和 autoprefixer 添加到你的 postcss.config.js 文件，或者在你的项目中配置 PostCSS 的任何地方。

postcss.config.js

module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  }
}

3、
配置模板路径
在 tailwind.config.js 文件中添加所有模板文件的路径。

tailwind.config.js

/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}

4、
将 Tailwind 指令添加到你的 CSS
将每个 Tailwind 层的 @tailwind 指令添加到你的主 CSS 文件中。

main.css

@tailwind base;
@tailwind components;
@tailwind utilities;


5、
开始构建进程
使用 npm run dev 或 package.json 文件中配置的任何命令运行构建进程。

Terminal

npm run dev

6、
开始在你的 HTML 中使用 Tailwind
确保编译后的 CSS 包含在 <head> 中（你的框架可能会为你处理），然后开始使用 Tailwind 的工具类来设置内容的样式。

index.html

<!doctype html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="/dist/main.css" rel="stylesheet">
</head>
<body>
  <h1 class="text-3xl font-bold underline">
    Hello world!
  </h1>
</body>
</html>