# 编写一个压缩构建资源为 zip 包的插件

## 准备知识:Node.js 里面将文件压缩为 zip 包

- 使用 jszip (https://www.npmjs.com/package/jszip)

```js
var zip = new JSZip();

zip.file("Hello.txt", "Hello World\n");

var img = zip.folder("images");

img.file("smile.gif", imgData, { base64: true });

zip.generateAsync({ type: "blob" }).then(function (content) {
  // see FileSaver.js
  saveAs(content, "example.zip");
});
```
