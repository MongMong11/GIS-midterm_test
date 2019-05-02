# GIS-midterm_test

備註：請把詳細操作步驟及過程寫出來，包含資料來源(odt/docx)，繳交時須包含所有 gpkg 檔案和輸出的 pdf 檔案(出圖)

#### 1. 請找出雪霸國家公園包含的行政區域有哪幾個鄉鎮市？

首先，下載[鄉鎮市區界線(TWD97經緯度)](https://data.gov.tw/dataset/7441?fbclid=IwAR0PuUxCtZK7320qEO5_QgSh8T7i4mMviSRxf2QJG8eZqtHV4c9qDZYei10)和老師所提供的國家公園邊界，檢察座標是否皆為WGS84，再使用"Intersection"，並勾選鄉鎮市和國家公園資料做交集，存檔成mid-term test 1.gpkg後，圖層右鍵點選"open attribute table",可了解到雪霸國家公園行政區域內有苗栗縣南庄鄉、新竹縣的尖石鄉和五峰鄉、苗栗縣泰安鄉，和臺中市的和平區。

#### 2. 請製作出花蓮縣境內非國家公園的區域向量圖

首先匯入之前老師所給的臺灣縣市邊界和國家公園邊界圖層，接下來使用"點選工具"點選花蓮縣，圖層點選右鍵，點選"Export" -> "Save Selected Feature As"重新存成一新的圖層，再使用"Difference"，差集花蓮縣圖層與國家公園邊界，存檔成mid-term test 2。

#### 3. 請找出國道三號總共經過哪幾個鄉鎮市（可參考圖資來源：交通部運輸研究所）

搜尋[交通網路地理資訊倉儲系統有關國道的資料](https://gist.motc.gov.tw/gist_web/MapDataService/Retrieval?fbclid=IwAR1dz_0o9glL8fjqIhZgXpAwh1_QMR83GnXC3611qQ7Tv0QW10-nCs0b1YM)，下載交通部所提供的SHP檔案，並匯入後調整座標成WGS84，並使用"Intersection"交集，得到交集圖層後，開啟"Open attribute Tables",即可得到交集的鄉鎮市資料。

**4. 苗栗線境內有許多低海拔山區為石虎的棲息地，最近三義外環道的開發可能造成石虎棲地破碎化，進而導致石虎滅絕，請嘗試使用 QGIS 來分析並探討下列問題：**

##### (1) 苗栗縣境內石虎主要分布的熱點為何？要如何使用公開資料來劃定分布熱[點（提示：可使用路殺社資料或是一些期刊研究報討公開資料）？請試著繪出石虎的分布範圍多邊形

石虎的[相關點位資料](https://www.tbn.org.tw/data/query?ft=biotaxonid%3A416107)由生物多樣性網路獲得粗略位置，之後將點位參考[匯入工作表或 CSV 檔](http://www.qgistutorials.com/zh_TW/docs/importing_spreadsheets_csv.html)文章，將點位先使用google表單事先處理過後，再匯入QGIS中，並使用"minimum bounding geometry"，選取"CONVEX_HULL"。

##### (2) 請依照上述的石虎分布範圍，使用環域(buffer)分析工具繪製 500 m 的緩衝區



##### (3) 請將上兩小題輸出一張石虎分布點位（點圖層）以及緩衝區的地圖


