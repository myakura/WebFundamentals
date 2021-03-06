project_path: /web/_project.yaml
book_path: /web/fundamentals/_book.yaml
description: 為儘快完成初次轉譯，我們需要將下列三種變數最佳化: 儘可能減少關鍵資源數量、儘可能減少關鍵位元組數以及儘量縮短關鍵路徑的長度。

{# wf_updated_on: 2014-04-27 #}
{# wf_published_on: 2014-03-31 #}

# 最佳化關鍵轉譯路徑 {: .page-title }

{% include "web/_shared/contributors/ilyagrigorik.html" %}



為儘快完成初次轉譯，我們需要將下列三種變數最佳化:

* **儘可能減少關鍵資源數量。**
* **儘可能減少關鍵位元組數。**
* **儘量縮短關鍵路徑的長度。**

關鍵資源是任何可能阻礙初次轉譯的資源。網頁上的關鍵資源越少，瀏覽器在螢幕上顯示內容時必須完成的工作量就越少，對 CPU 和其他資源的佔用也相對變手。

同樣地，瀏覽器必須下載的關鍵位元組越少，就能越快處理內容並顯示在螢幕上。如要減少位元組數量，我們可以從減少資源數量著手 (刪除相應資源或者將其設為非關鍵資源)；同時還可壓縮及最佳化各項資源，儘可能降低傳輸量。

最後，關鍵路徑長度是網頁所需的所有關鍵資源與其位元組大小之間的依賴圖功能: 有些資源只能在上一個資源處理完畢後才會開始下載，並且資源越大，下載所需的往返次數就越多。

換句話說，資源數量、位元組數和關鍵路徑長度相互關聯，但是並不完全相同。舉例來說，您也許無法減少關鍵資源數量，或者無法縮短關鍵路徑長度，但是減少關鍵位元組數量，對於最佳化仍有正面幫助；反之亦然。

**最佳化關鍵轉譯路徑的常見步驟如下: **

1. 分析及描述關鍵路徑: 資源數量、位元組數、長度。
 2. 盡量減少關鍵資源數量: 刪除相應資源、延遲下載、標記為非同步資源等等。
3. 最佳化剩餘關鍵資源的載入順序: 您需要儘早下載所有關鍵資源，以縮短關鍵路徑長度。
4. 盡量減少關鍵位元組數，以縮短下載時間 (往返次數)。
