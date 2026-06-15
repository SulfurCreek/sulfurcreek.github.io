# CLAUDE.md

提供給 Claude Code 在這個 repo 工作時的指引。

## 這是什麼

Sulfur Creek（台北 pop-punk 樂團）的單頁 EPK 網站，中英雙語。線上版：https://sulfurcreek.github.io/

## 怎麼跑、怎麼發佈

- 純靜態網站，**沒有 build、沒有測試、不用裝套件**。
- 本地預覽：`open index.html` 就好。
- **`git push origin main` 就會自動發佈**到線上（GitHub Pages，約 1~2 分鐘）。沒有測試環境。
- `.nojekyll` 是空檔案，用來叫 GitHub Pages 直接出檔案、不要動它。

## 檔案怎麼放

- [index.html](index.html)：整個頁面 + 底部的小 `<script>`（年份、捲動動畫、點擊追蹤）。
- `assets/`：圖片（`logo.png` 和各區塊 jpg）、`styles.css`。
- `audio/`：`sink-or-swim.mp3`，Listen 區塊的播放器在播這個。
- 全部用相對路徑引用。

## 注意事項（容易踩雷）

- **不要把圖片或 CSS 改回 base64 內嵌**。這些是特地抽出來讓 index.html 保持小又好讀的。新圖片就放 `assets/` 當檔案。
- 中文文案放在英文段落裡的 `<span class="zh">…</span>`，改字時中英要一起改。
- 點擊追蹤：新的連結或按鈕加上 `data-track="名稱"`，底部的 script 會自動接上 Abacus 計數。
- 改完用瀏覽器打開看一下圖片、播放器、影片、連結正常就好。
