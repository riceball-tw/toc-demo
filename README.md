# [Intersection Observer 真實案例：自動更新目錄](https://www.webdong.dev/post/real-use-case-of-intersection-observer-toc/)

## 前言

近期製作到內容大綱（Table of Contents）相關的功能，發現是一個很適合使用 Intersection Observer 的案例，透過監聽特定元素來自動更新目錄的狀態。
在早期可能會需要透過 getBoundingClientRect 之類的方法來計算元素有沒有離開視窗，但隨著專門偵測元素是否進入視窗的 API 出現，這樣的需求就變得更加容易實現。

## 問題

製作一個可以根據特定元素內的標題生成目錄清單的功能，並且清單會根據滑動位置適當的顯示激活樣式：

- 可自動根據目前文章中的內容生成對應的目錄連結清單並顯示在側欄
- 當使用者滾動到對應區塊時，自動更新目錄激活的狀態
- 當使用者點擊目錄連結時，滾動到對應的位置
