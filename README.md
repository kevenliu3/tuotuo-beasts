# tuotuo-beasts

坨坨神兽养成小程序的插画 CDN 仓库，通过 jsDelivr 直接引用（小程序单包上限 2MB，图不能进包）。

```
https://cdn.jsdelivr.net/gh/kevenliu3/tuotuo-beasts@main/<目录>/<文件名>.jpg
```

## 目录

| 目录 | 内容 | 说明 |
|---|---|---|
| 根目录 | 山海经神兽（30 只） | `<id>.jpg`，与 `utils/beasts.js` 的 id 对应 |
| `fish/` | 池塘鱼（24 种） | `<id>.jpg`，与 `utils/fishes.js` 对应 |
| `hamster/` | 仓鼠（17 种） | `<id>.jpg`，与 `utils/hamsters.js` 对应 |

## 规格

统一 **512×512 JPEG**，质量 86，单张 25~45KB，整目录 632KB。

仓鼠这批是**写实照片风格**（爸爸明确要求「图片要真实」）—— 毛色按真实品种来，
不是卡通插画：三线有背线、银狐近乎纯白、玳瑁熊是黑黄斑块、卷毛熊是卷毛、
黑丝绒熊通体墨黑泛丝光。

## 加图 / 换图

1. 用 ImageGen 生成 1024×1024 写实照片，**右下角会带 AI 水印**；
2. 跑小程里的 `tools/hamster_art.py <原图目录> <本仓目录>`：裁掉右下 96px 水印 →
   缩放 512×512 → JPEG；
3. 文件名用 `<品种 id>.jpg`，commit + push 到 `main`；
4. 生产环境记得把 `cdn.jsdelivr.net` 加进小程序后台的 downloadFile 合法域名。

原图（1024 版）不进本仓，留在仓外 `../hamster_raw_src/`，要重裁时用。
