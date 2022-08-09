```js
function download(url, name) {
  const a = document.createElement("a");
  a.download = name;
  a.rel = "noopener";
  a.href = url;
  // 触发模拟点击
  a.dispatchEvent(new MouseEvent("click"));
  // 或者 a.click()
}

const json = {
  a: 3,
  b: 4,
  c: 5,
};
const str = JSON.stringify(json, null, 2);

// 方案一：Text -> DataURL
const dataUrl = `data:,${str}`;
download(dataUrl, "demo.json");

// 方案二：Text -> Blob -> ObjectURL(推荐)
const url = URL.createObjectURL(new Blob(str.split("")));
download(url, "demo1.json");
```