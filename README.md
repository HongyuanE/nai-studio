# NAI Studio

一个自用的 NovelAI 生图前端，单个 `index.html`，没有后端。

**API Key 只存在你自己浏览器的 localStorage 里**，请求从浏览器直接发往 `image.novelai.net` / `api.novelai.net`，不经过任何其他服务器。换设备或换浏览器要重新填一次；点页面右上角 `Key` → 清除 可以删掉。

## 功能（按 2026-10 官网的请求格式复刻）

- 模型：V5 Full（Effort High / Medium）、V5 Curated、V4.5 Full、V4.5 Curated；Mode：Anime / Furry
- Prompt + Quality Tags 预设、Undesired Content + UC 预设、透明背景（V5）
- 角色 Character Prompts：每个角色独立的 prompt / UC，AI's Choice 或自定义位置（V5 自由定位，V4.5 吸附 5×5 网格）
- 参考图：Image2Image（strength / noise）、Vibe Transfer、Precise Reference（后两者 V5 暂不支持，官网也一样，添加时会自动切到 V4.5）
- 分辨率预设 Normal / Large / Wallpaper / Small / Custom，张数 1–4，Steps、Guidance、Rescale、Seed、Sampler
- Inpaint：在底图上用手指 / Apple Pencil / 鼠标涂蒙版，只重画涂过的区域，其余像素保持原图
- Enhance（放大倍数 + Magnitude 1–5）、Upscale ×2
- 导入图片：读取 NovelAI 图片里的参数（PNG tEXt、WebP EXIF、stealth alpha），还原 Prompt / UC / 角色 / 设置 / Seed；也可以把图片当 Img2Img、Vibe 或 Precise Reference
- 下载的 PNG 带有 NovelAI 元数据，可以再导入回来（本站或官网）
- 生成按钮上显示预估 Anlas（官网同一公式），历史图保存在浏览器 IndexedDB

## 本地运行

```bash
python -m http.server 8000
```

然后打开 <http://localhost:8000>。也可以直接双击 `index.html`，但余额显示可能因为跨域拿不到。
