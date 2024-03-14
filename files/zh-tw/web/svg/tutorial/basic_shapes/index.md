---
title: 基本圖形
slug: Web/SVG/Tutorial/Basic_Shapes
---

{{SVGRef}}

{{ PreviousNext("Web/SVG/Tutorial/Positions", "Web/SVG/Tutorial/Paths") }}

大部分的 SVG 繪圖都會使用幾種基本形狀。這些形狀的目的從名稱就可以看出來。此文章會說明一些決定其位置和大小的參數，但元素的參考資料可能會包含更精確和完整的描述，以及其他在此文章中不會涵蓋的屬性。然而，由於它們在大部分的 SVG 檔案中都會被使用，因此有必要對它們進行一些介紹。

若要插入圖形，您需要在檔案中建立元素。不同的元素對應不同的形狀，並且需要不同的參數來描述這些形狀的大小和位置。有些元素可以由其他形狀建立而略顯多餘，但都是為了讓您方便使用，並且讓您的 SVG 檔案盡可能簡短和易讀。所有的基本形狀都顯示在下圖中。

![八個不同的圖形和繪圖。最上層為黑色框線的方形和圓角方形，下一層為紅色框線的圓形和橢圓形，下一層為黃色的直線和鋸齒線，下一層為綠色框線的星形，最後一層為藍色曲線。](shapes.png)

產生該圖片的程式碼如下：

```xml
<?xml version="1.0" standalone="no"?>
<svg width="200" height="250" version="1.1" xmlns="http://www.w3.org/2000/svg">

  <rect x="10" y="10" width="30" height="30" stroke="black" fill="transparent" stroke-width="5"/>
  <rect x="60" y="10" rx="10" ry="10" width="30" height="30" stroke="black" fill="transparent" stroke-width="5"/>

  <circle cx="25" cy="75" r="20" stroke="red" fill="transparent" stroke-width="5"/>
  <ellipse cx="75" cy="75" rx="20" ry="5" stroke="red" fill="transparent" stroke-width="5"/>

  <line x1="10" x2="50" y1="110" y2="150" stroke="orange" stroke-width="5"/>
  <polyline points="60 110 65 120 70 115 75 130 80 125 85 140 90 135 95 150 100 145"
      stroke="orange" fill="transparent" stroke-width="5"/>

  <polygon points="50 160 55 180 70 180 60 190 65 205 50 195 35 205 40 190 30 180 45 180"
      stroke="green" fill="transparent" stroke-width="5"/>

  <path d="M20,230 Q40,205 50,230 T90,230" fill="none" stroke="blue" stroke-width="5"/>
</svg>
```

> **附註：**`stroke`、`stroke-width` 和 `fill` 屬性會在後面的章節解說。

## 矩形

{{SVGElement("rect")}} 元素會在畫面上繪製一個矩形。有六個基本屬性可以控制畫面上矩形的位置和形狀。右邊的矩形設定了 `rx` 和 `ry` 圓角參數。未設定的話，預設為 `0`。

```xml
<rect x="10" y="10" width="30" height="30"/>
<rect x="60" y="10" rx="10" ry="10" width="30" height="30"/>
```

- `x`
  - ：矩形左上角的 x 座標。
- `y`
  - ：矩形左上角的 y 座標。
- `width`
  - ：矩形寬度。
- `height`
  - ：矩形高度。
- `rx`
  - ：矩形邊角的 x 半徑。
- `ry`
  - ：矩形邊角的 y 半徑。

## 圓形

{{SVGElement("circle")}} 會在畫面上繪製一個圓形。需要三個基本參數來決定形狀和位置。

```xml
<circle cx="25" cy="75" r="20"/>
```

- `r`
  - ：圓的半徑。
- `cx`
  - ：圓心的 x 座標。
- `cy`
  - ：圓心的 y 座標。

## 橢圓形

{{SVGElement("ellipse")}} 比起 {{SVGElement("circle")}} 元素更加通用，您可以分別縮放圓的 x 半徑和 y 半徑（數學名詞為半長軸和半短軸）。

```xml
<ellipse cx="75" cy="75" rx="20" ry="5"/>
```

- `rx`
  - ：橢圓的 x 半徑。
- `ry`
  - ：橢圓的 y 半徑。
- `cx`
  - ：圓心的 x 座標。
- `cy`
  - ：圓心的 y 座標。

## 直線

{{SVGElement("line")}} 元素取兩個點的座標作為參數，並在它們之間繪製一條直線。

```xml
<line x1="10" x2="50" y1="110" y2="150" stroke="black" stroke-width="5"/>
```

- `x1`
  - ：點 1 的 x 座標。
- `y1`
  - ：點 1 的 y 座標。
- `x2`
  - ：點 2 的 x 座標。
- `y2`
  - ：點 2 的 y 座標。

## 多段線

{{SVGElement("polyline")}} 是一組連接在一起的直線。因為點的清單可能會很長，所有點都包含在一個屬性中：

```xml
<polyline points="60, 110 65, 120 70, 115 75, 130 80, 125 85, 140 90, 135 95, 150 100, 145"/>
```

- `points`
  - ：點的清單。每個數字必須用空白、逗號、結束命令符或換行符分隔，允許額外空白。每個點必須包含兩個數字：x 座標和 y 座標。因此，清單 `(0,0)`、`(1,1)` 和 `(2,2)` 可以寫成 `0, 0 1, 1 2, 2`。

## 多邊形

{{SVGElement("polygon")}} 與 {{SVGElement("polyline")}} 類似，都是由連接一系列點的線段構成。但 `polygon` 的路徑會自動將最後一個點和第一個點連起來，形成封閉形狀。

> **附註：**矩形也是多邊形的一種，因此多邊形可以用來建立一個沒有圓角的 `<rect/>` 元素。

```xml
<polygon points="50, 160 55, 180 70, 180 60, 190 65, 205 50, 195 35, 205 40, 190 30, 180 45, 180"/>
```

- `points`
  - ：點的清單。每個數字必須用空白、逗號、結束命令符或換行符分隔，允許額外空白。每個點必須包含兩個數字：x 座標和 y 座標。因此，清單 `(0,0)`、`(1,1)` 和 `(2,2)` 可以寫成 `0, 0 1, 1 2, 2`。接著圖形會自動閉合路徑，所以最後一條直線會從 `(2,2)` 繪製到 `(0,0)`。

## 路徑

{{SVGElement("path")}} 是 SVG 中最通用的形狀。您可以使用 `path` 元素來繪製矩形（不論圓角）、圓形、橢圓形、折線和多邊形。基本上任何其他形狀、貝茲曲線、二次方曲線等等都可以使用 `path` 元素來繪製。

因此，本教學的[下一節](/zh-TW/docs/Web/SVG/Tutorial/Paths)將聚焦在路徑上。現在請記住用來控制形狀的參數。

```xml
<path d="M20,230 Q40,205 50,230 T90,230" fill="none" stroke="blue" stroke-width="5"/>
```

- `d`
  - ：點的清單，以及如何繪製路徑的其他資訊。請參閱[路徑](/zh-TW/docs/Web/SVG/Tutorial/Paths)章節以了解更多資訊。

{{ PreviousNext("Web/SVG/Tutorial/Positions", "Web/SVG/Tutorial/Paths") }}
