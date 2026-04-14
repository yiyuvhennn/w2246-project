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