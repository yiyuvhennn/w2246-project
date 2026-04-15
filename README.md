# W2246 線上活動資訊展示頁

本專案為 **W2246 單頁活動介紹頁面**，使用 **Vue 3 + Vite** 開發，依據業主提供之 UI 參考與內容素材，完成單頁式活動資訊展示頁實作。

頁面重點包含活動主視覺、適合對象、課程成果、學習目標、師資介紹、課程大綱與行動呼籲區塊，並支援桌機、平板與手機版瀏覽。

---

## 專案目標

本案目標為完成一頁式【線上活動資訊展示頁】，讓使用者可以清楚閱讀活動資訊，並透過單頁式排版建立完整的瀏覽流程。

此專案對應的重點包含：

- 單頁活動介紹頁製作
- 區塊式 section 規劃
- RWD 響應式切版（桌機 / 平板 / 手機）
- 前端完整畫面實作
- 原始碼整理與簡易使用說明

---

## 專案特色

- 依據設計稿進行前端切版實作
- 採用元件化架構，方便維護與後續調整
- 使用資料驅動方式管理頁面內容
- 支援 desktop / tablet / mobile 響應式版面
- 包含漸層文字、漸層 icon、hover 動效與裝飾圖形定位
- 適合作為活動頁、課程頁、品牌展示型 landing page 參考

---

## 使用技術

- Vue 3
- Vite
- JavaScript
- CSS3

---

## 頁面區塊

本專案主要包含以下內容區塊：

- Hero 主視覺區
- 適合學生 / 課程成果
- 學習目標
- 師資介紹
- 課程大綱
- CTA 行動呼籲區塊

---

## 專案結構

```text
w2246-project/
├─ public/
│  ├─ assets/
│  │  ├─ icon/
│  │  └─ images/
│  └─ background/
│     ├─ desktop.svg
│     ├─ tablet.svg
│     └─ phone.svg
├─ src/
│  ├─ components/
│  │  ├─ CtaSection.vue
│  │  ├─ GoalCard.vue
│  │  ├─ GoalsSection.vue
│  │  ├─ HeroSection.vue
│  │  ├─ HighlightsSection.vue
│  │  ├─ ScheduleSection.vue
│  │  ├─ SectionTitle.vue
│  │  ├─ SessionCard.vue
│  │  └─ TeacherSection.vue
│  ├─ data/
│  │  └─ eventData.js
│  ├─ App.vue
│  ├─ main.js
│  └─ styles.css
├─ index.html
├─ package.json
└─ vite.config.js

第一次使用前請先確認

如果你是第一次開這個專案，請先確認電腦已安裝以下工具：

Node.js
npm（通常安裝 Node.js 時會一起安裝）
如何確認是否安裝成功

打開終端機後輸入：

node -v
npm -v

如果畫面有出現版本號，例如 v22.x.x、10.x.x，就代表已經安裝成功。
如果沒有出現版本號，請先安裝 Node.js。

如何在本機開啟專案
1. 下載專案

先把專案下載或解壓縮到你的電腦。

2. 打開終端機

在專案資料夾所在位置打開終端機。

3. 進入專案資料夾

例如：

cd w2246-project
4. 安裝套件

第一次執行時，請先安裝專案所需套件：

npm install
5. 啟動開發環境
npm run dev
6. 開啟瀏覽器

終端機通常會顯示一個本機網址，例如：

http://localhost:5173

把它貼到瀏覽器打開，就可以看到頁面。

常用指令
啟動開發模式
npm run dev
打包正式版本
npm run build
預覽打包結果
npm run preview
資料管理方式

本專案內容主要由 src/data/eventData.js 統一管理，包含：

Hero 文案
快速資訊卡
適合對象
課程成果
學習目標
師資資料
課程大綱
CTA 文案

透過資料與元件分離的方式，可以在不大幅修改畫面結構的情況下，快速替換活動內容。

實作重點
1. 元件化切版

將各 section 拆分成獨立元件，讓畫面結構更清楚，也方便後續針對單一區塊調整。

2. 響應式設計

根據裝置尺寸切換背景、間距、欄數與卡片排法，確保桌機與行動裝置都能正常瀏覽。

3. 視覺細節還原

頁面包含以下視覺細節：

漸層文字
漸層 icon
卡片陰影與圓角
裝飾圖形定位
hover 動效
狀態型 icon 視覺處理
4. 單頁式閱讀流程

以單頁方式整合活動資訊，讓使用者可以由上到下完整閱讀活動內容與課程資訊。

交付內容對應

本專案可對應以下交付重點：

初次檢核內容
頁面 section 結構規劃
RWD 切版方式說明（手機 / 平板 / 桌機）
最終交件內容
完整前端頁面
RWD 成果
原始碼
簡易使用說明
補充說明
npm install 通常只需要在第一次下載專案後執行一次
npm run dev 是開發時最常用的指令
如果畫面沒有更新，可以重新整理瀏覽器
如果終端機顯示錯誤，請先確認是否已成功安裝 Node.js 與 npm
若需修改活動內容，優先調整 src/data/eventData.js
若需調整畫面樣式，主要修改 src/styles.css