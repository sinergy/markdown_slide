
Markdown Slide for Starktech Co Ltd
===================================

## 投影片設置

大多數能夠自訂的設置選項都在 [`slide_config.js`](slide_config.js) 這個檔案中
這些設置選項包含了：
- 投影片標題
- Google Analytics 的 Traking ID
- 演說者資訊(姓名、社群檔案、部落格)
- 使用的 Web Fonts
- 佈景主題

## 編輯 CSS

推薦使用 [Compass](http://compass-style.org/)，不但安裝簡單且非常容易使用與上手

### 安裝 Compass 並且開始修改

首先安裝 compass:

    sudo gem update --system
    sudo gem install compass

接著，您可以透過下列指令監看您對 [`/theme/scss`](theme/scss) 資料夾中的任何檔案所進行的修改或是新增任何檔案所帶來的效果：

    $ cd markdown-slide
    $ compass watch

這個指令將會在您修改檔案時，自動重新編譯 .scss 檔案，而其相對應的 .css 檔案，也將自動地被輸出到 [`/theme/css`](theme/css) 資料夾中

預設上，在主要專案資料夾中的 [`config.rb`](config.rb) 會輸出精簡化的 .css 檔案，這是撰寫網頁的最佳實務之一！然而，若您不希望或不需要精簡化過後的 .css 檔案，請執行以下指令：

    compass watch -s expanded

*註：* 您不需要去修改 [`_base.scss`](theme/scss/_base.scss) 這個檔案

## 瀏覽投影片

這份投影片可以藉由 `file://` 的 protocol 在本機端執行，使得在撰寫與開發上便利許多 :p

### 在 Web Server 上執行

在某些特殊的場合或狀況下，你可能會需要一台 Web Server，這時可以執行 [`serve.sh`](serve.sh) 這支 shell script。 它會替你建立一個在本機端運行的 Web Server，並且開啟您預設的瀏覽器，並導向 [`http://localhost:8000/template.html`](http://localhost:8000/template.html):

    $ cd markdown-slide
    $ ./serve.sh

您也可以指定特定連接埠（port）:

    $ ./serve.sh 8080

### 簡報者模式

本投影片包含了一個在彈出式視窗下，用來**檢視**＆**控制**投影片的簡報者模式

若要啟用該模式的話，請在 URL 的末端加上 `presentme=true`，如： [http://localhost:8000/template.html?presentme=true](http://localhost:8000/template.html?presentme=true)

若要停用該模式的話，請修改參數值為 `presentme=false`，如： [http://localhost:8000/template.html?presentme=false](http://localhost:8000/template.html?presentme=false)

簡報者模式一旦設定，就算是重新整理網頁，也會沿用之前設定過的簡報者模式，若要回復初始設定，請設定 `presentme=false`

---

註：本投影片採用並修改自 Google 在 Google I/O 2012 上所提供的 [HTML 5 投影片模版](https://code.google.com/p/io-2012-slides/)