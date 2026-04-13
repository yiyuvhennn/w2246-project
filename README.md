# W2246 線上活動資訊展示頁 Starter

這份 starter 以 **Vue 3 + Vite** 建立，目的不是 100% 還原 Figma，而是讓你今天就能開工：

- 已先拆好 section 結構
- 已先做好 RWD 骨架
- 已先整理成資料驅動渲染
- 已先放入一張從設計檔抽出的講者素材

## 我從 ZIP 推到的重點

### 已知需求
- 需要活動資訊展示頁
- 核心內容包含：活動介紹、講者、時程安排
- 需支援桌機 / 平板 / 手機
- 需處理字體、icon、圖片、hover 效果
- 交付內容包含完整前端頁面、RWD、原始碼與簡易說明

### 從 Figma thumbnail 推測的設計方向
- 使用亮色漸層與深色塊搭配
- 有完整色票與灰階系統
- 有 4 張講者卡片的排法
- 講者卡底部有深色標籤條
- 整體視覺偏乾淨、留白多、資訊模組化

> 注意：`.fig` 是本機封存格式，這裡無法像線上 Figma 檔那樣直接逐層檢視，所以這份 starter 是「高可信骨架版」，等你打開正式 Figma 後再補字體、間距、精準尺寸。

## 專案結構

```text
w2246-starter/
├─ public/
│  └─ assets/
│     └─ speaker-amy.png
├─ src/
│  ├─ components/
│  │  ├─ AppFooter.vue
│  │  ├─ AppHeader.vue
│  │  ├─ CtaSection.vue
│  │  ├─ HeroSection.vue
│  │  ├─ HighlightsSection.vue
│  │  ├─ ScheduleSection.vue
│  │  ├─ SpeakerCard.vue
│  │  └─ SpeakersSection.vue
│  ├─ data/
│  │  └─ eventData.js
│  ├─ App.vue
│  ├─ main.js
│  └─ styles.css
├─ index.html
├─ package.json
└─ vite.config.js
```

## 今天就能開工的順序

1. 先跑起來：
   ```bash
   npm install
   npm run dev
   ```
2. 打開正式 Figma，比對：
   - 字體
   - 邊距 / 欄寬
   - 卡片圓角
   - 色碼
3. 優先修正 Hero 與 Speaker Card
4. 再修 Schedule 區與 CTA 區
5. 最後補 hover / 動態 / icon

## 建議你下一步先改哪裡

- `src/data/eventData.js`
  - 換正式活動文案
  - 換講者資料
  - 換議程資料
- `src/styles.css`
  - 套正式色碼 / 間距 / 陰影 / 字體
- `src/components/SpeakerCard.vue`
  - 對齊 Figma 講者卡細節
- `src/components/HeroSection.vue`
  - 套正式主視覺與 CTA 內容

## 如果你要再往上升級

可以接著加：
- Sticky section nav
- 議程 tab 切換
- FAQ 區
- 報名表單 modal
- GSAP / Intersection Observer 進場動畫
