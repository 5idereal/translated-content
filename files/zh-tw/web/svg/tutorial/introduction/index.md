---
title: 引言
slug: Web/SVG/Tutorial/Introduction
page-type: guide
---

{{SVGRef}}

{{ PreviousNext("Web/SVG/Tutorial", "Web/SVG/Tutorial/Getting_Started") }}

[SVG](/zh-TW/docs/Web/SVG) 是一種 [XML](/zh-TW/docs/Web/XML) 語言，類似於 [XHTML](/zh-TW/docs/Glossary/XHTML)，可用於繪製像下圖的向量圖形。它可以指定所有必要的線條和形狀來建立圖片、修改現有的點陣圖片，或一起使用。圖片及其元件也可以進行變形、合成，或套用濾鏡來改變外觀。

![Mozilla dino logo](dino.svg)

SVG 於 1999 年誕生，在此之前，有幾個相互競爭的格式被送交到 [W3C](https://www.w3.org)，但是都沒有被完全批准。所有主流[瀏覽器](https://caniuse.com/#search=svg)皆支援 SVG。SVG 的缺點是載入緩慢。但 SVG 也有優點，比如有 [DOM 介面](/zh-TW/docs/Web/API)可用，且不需要安裝第三方擴充功能。是否使用 SVG 通常取決於你的用途。

## Basic ingredients

[HTML](/en-US/docs/Web/HTML) provides elements for defining headers, paragraphs, tables, and so on. In much the same way, SVG provides elements for circles, rectangles, and simple and complex curves. A simple SVG document consists of nothing more than the {{ SVGElement('svg') }} root element and several basic shapes that build a graphic together. In addition, there is the {{ SVGElement('g') }} element, which is used to group several basic shapes together.

Starting from this basic structure, the SVG image can become arbitrarily complex. SVG supports gradients, rotations, filter effects, animations, interactivity with JavaScript, and so on. But all these extra features of the language rely on this relatively small set of elements to define the graphics area.

## 開始前

There are a number of drawing applications available, such as [Inkscape](https://inkscape.org/), which are free and use SVG as their native file format. However, this tutorial will rely on the trusty XML or text editor (your choice). The idea is to teach the internals of SVG to those who want to understand it, and that is best done by dirtying your hands with a bit of markup. You should note your final goal though. Not all SVG viewers are equal and so there is a good chance that something written for one app will not display exactly the same in another, because they support different levels of the SVG specification or another specification that you are using along with SVG (that is, [JavaScript](/en-US/docs/Web/JavaScript) or [CSS](/en-US/docs/Web/CSS)).

有許多繪圖應用程式可供使用，例如 [Inkscape](https://inkscape.org/) —— 免費且使用 SVG 作為原生檔案格式。但本教學只會使用 XML 或文字編輯器（由你選擇），我們的目的是向那些想要了解 SVG 的人傳授基本原理，而最好的方法就是自己親自動手操作。

SVG is supported in all modern browsers and even a couple versions back in some cases. A fairly complete browser support table can be found on [Can I use](https://caniuse.com/svg). Firefox has supported some SVG content since version 1.5, and that support level has been growing with each release since. Hopefully, along with the tutorial here, MDN can help developers keep up with the differences between Gecko and some of the other major implementations.

所有現代瀏覽器都支援 SVG，有些甚至幾個版本前就開始支援了。你可以在 [Can I use](https://caniuse.com/#feat=svg) 上找到完整的瀏覽器支援表格。Firefox 自 1.5 版支援 SVG 的部分內容，並且支援的程度越來越高。希望透過本教學，MDN 能幫助開發者理解 Gecko 內核和其他一些主要實作間的差異。

Before starting you should have a basic understanding of XML or another markup language such as HTML. If you are not too familiar with XML, here are some guidelines to keep in mind:

- SVG elements and attributes should all be entered in the case shown here since XML is case-sensitive (unlike HTML).
- Attribute values in SVG must be placed inside quotes, even if they are numbers.

SVG is a huge specification. This tutorial attempts to cover the basics. Once you are familiar, you should be able to use the [Element Reference](/en-US/docs/Web/SVG/Element) and the [Interface Reference](/en-US/docs/Web/API/Document_Object_Model#svg_interfaces) to find out anything else you need to know.

## SVG 版本

自 2003 年成為推薦後，最新的「完整」SVG 版本是 1.1。基於 SVG 1.0，並提升模組化程度以便於實作。[SVG 1.1 的第二版](https://www.w3.org/TR/SVG/)在 2011 年成為推薦。「完整」SVG 1.2 原為 SVG 的下一個主要版本，但被即將發佈，目前仍在開發的 [SVG 2.0](https://www.w3.org/TR/SVG2/) 取代，其採用類似 CSS3 的方案，將元件拆分成數個鬆散耦合的規格。

除了完整的 SVG 推薦，W3C 的工作小組於 2003 年推出了 SVG Tiny 和 SVG Basic。這兩個設定欓主要針對行動裝置。SVG Tiny，能夠為低效能的小型裝置提供圖形基元。SVG Basic 提供了許多完整 SVG 的功能，但不包括難以實現或轉譯負荷過重的功能（如動畫）。SVG Tiny 1.2 於 2008 年成為 W3C 的推薦。

曾有制定 SVG 印刷規格的計畫，加入多頁面支援和增強色彩管理，但已經中止。

{{ PreviousNext("Web/SVG/Tutorial", "Web/SVG/Tutorial/Getting_Started") }}
