# 臉部辨識使用深度學習範例專案

<p>此為使用Python3程式語言撰寫臉部辨識範例專案，使用Keras操作Tensorflow，並使用CNN 神經網絡模型建置之深度學習應用。</p>

<p>
本專案使用 Google Colaboratory 撰寫開發，將ipynb放置到自己的Google雲端硬碟內，在Google雲端硬碟網頁視窗開啟檔案即可使用。 <br/>
使用 Google Colaboratory 提供TPU進行深度學習運算。
</p>

<p></p>
可參考資源：
[欢迎使用 Colaboratory](https://colab.research.google.com/notebooks/welcome.ipynb)


專案程式版本：
----------------------------------------------------------------------------------------------------------------------------------
**1. Face_Recognition_TPU_Demo.ipynb** --> 使用掛載自己Google雲端硬碟方式，取得圖片資料透過自己Google雲端硬碟內部位置之設置取得。<br/>
此版本需要自己Google雲端硬碟帳戶授權控制。<br/>

<p></p>

**2. Face_Recognition_TPU_fp16_datazip_Demo.ipynb 和 Face_Recognition_TPU_fp32_datazip_Demo.ipynb** --> 透過下載指定連結網路位址，取得已包裝成壓縮檔形式圖片資料檔。<br/>

fp16:資料小數浮點精度為float16。<br/>
fp32:資料小數浮點精度為float32。<br/>

此版本使用的圖片資料集存放位置：<br/>
imgdata.zip：https://drive.google.com/open?id=19fvYcCAslDET2dP1SrwS2XAMOYGi4dgD  <br/>
(此連結可能會失效，如已失效請自行建立各自檔案連結)<br/>

imgdata.zip內部檔案結構：<br/>
內容為一個imgdata目錄資料夾，裡面存放"FaceImg"(訓練用圖片) 、"Facelabeldb"(分類索引編碼存放資料庫SQLite3檔案)、"PredictFaceimg"(預測用圖片) 三個目錄資料夾。<br/>

關於下載Google雲端硬碟共用檔案方法，可參考[Download Google Drive file with WGET](https://gist.github.com/iamtekeste/3cdfd0366ebfd2c0d805) <br/>
 
撰寫流程步驟劃分如下：
----------------------------------------------------------------------------------------------------------------------------------
1. 讀取圖片<br/>
2. 資料處理<br/>
3. 建立模型<br/>
4. 訓練模型<br/>
5. 畫出訓練過程圖片<br/>
6. 評估模型<br/>
7. 儲存模型和權重<br/>
8. 驗證模型(預測)
</p>

臉部圖片資料集與設置：
----------------------------------------------------------------------------------------------------------------------------------
<p>使用臉部圖片資料集原始來源：<br/>
[Celebrity-Face-Recognition-Dataset]https://github.com/prateekmehta59/Celebrity-Face-Recognition-Dataset </p>

<p>
使用 6 位名人的臉部圖片作為資料集來源使用，清單如下：<br/>
1. 'Aaron Judge'<br/>
2. 'Ben Stiller'<br/>
3. 'Ice Cube'<br/>
4. 'Adam Sandler'<br/>
5. 'Emily Watson'<br/>
6. 'Jean Reno'<br/>
</p>

<p>
臉部預測樣本設定： <br/>
每一位名人取出 4 張未存在訓練樣本裡臉部圖片，作為後面模型預測來源依據。
</p>
