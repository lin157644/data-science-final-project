# Introduction to Data Science - Group21_Music&nbsp;Popularity&nbsp;Prediction

## Final project midterm report

### Introduction

&emsp;&emsp;當今音樂串流平台的普及促使人們更傾向使用串流服務聆聽音樂。這種趨勢不僅節省成本，也更加便捷。以Spotify為例。透過預測歌曲流行程度，我們可以協助音樂家決定歌曲上架與廣告策略，同時為串流平台提供熱門音樂推薦的重要參考依據。
&emsp;&emsp;我們預計透過音樂串流平台提供的開放API，獲取歌曲相關資訊，包括作者、專輯、年份和風格等，以及利用預覽片段和外部資料集輔助，量化音樂特徵，例如歌唱比例、音調和動態範圍等，以達成預測歌曲流行程度的目標。

### Dataset

* [**Kaggle: Spotify Tracks Dataset**](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset)
    * 125種不同流派
    * \> 11000 筆歌曲資料
    * 包含預先量化的音訊特徵
* [**Spotify API**](https://developer.spotify.com/documentation/web-api/reference/get-track)
    * `https://api.spotify.com/v1/tracks/{id}`
      `preview_url` : A link to a 30 second preview (MP3 format) of the track.

### Current progress

閱讀相關論文，分析與討論要用哪種演算法來訓練模型
目前考量到的相關演算法包括: 決策樹、隨機森林、線性回歸、SVM等等
參考的方法: ++Predicting Music Popularity Using Music Charts++[^PredictingMusicPopularity]
* **數據收集**
  &emsp;&emsp;Spotify的Web API收集來自"Top 50 Global lists"的數據，包括榜單的排名、排名日期、歌手名稱、歌曲標題、歌曲發行日期、歌曲時長、歌曲30秒試聽的URL、歌曲是否包含不雅語言、流行度分數。
* **數據處理和特徵提取**
  &emsp;&emsp;使用Python套件LibROSA來提取五個聲學資訊，包括Mel-Frequency Cepstral Coefficients(MFCC), spectral centroid, spectral flatness, zero crossings,和節奏。
* **實例提取**
  &emsp;&emsp;對每天的榜單，將其中受歡迎的Top 50歌曲視為正實例，未被選中的歌曲視為負實例
* **模型訓練**
    * 使用不同的模型，包括AdaBoost、XGBoost、隨機森林、Naive Bayes(Gaussian和Bernoulli)、和SVM(使用RBF核心函數)，對處理後的數據進行訓練。
    * 此論文最終有最好結果的模型是使用所有可用數據並使用以RBF為核心函數的SVM分類器訓練的模型。

### Schedule

預計行程規劃:

1. 決定要針對音訊特徵還是音樂類型與排行等等進行分析
2. 透過研討相關論文探討數據的分佈，找出與目標預測之間可能的相關性
3. 蒐集相關的資料集，並對資料進行清理、篩選等前處理
4. 選擇適合的模型並進行訓練
5. 評估模型訓練出來的結果是否符合預期，進一步根據評估結果去調整參數、特徵或是模型來達到更好的預測結果
6. 將結果以視覺化的方式呈現，並撰寫專題報告

### What do you expect to accomplish by the end of semester

* 學會針對研究議題蒐集、選擇對應的資料集，及如何對數據進行前處理
* 希望能藉由音樂流行度分析，更加具體了解不同演算法的優勢、限制及適用情境。

[^PredictingMusicPopularity]: C. V. Soares Araujo, M. A. Pinheiro de Cristo and R. Giusti, "Predicting Music Popularity Using Music Charts," 2019 18th IEEE International Conference On Machine Learning And Applications (ICMLA), Boca Raton, FL, USA, 2019, pp. 859-864, doi: 10.1109/ICMLA.2019.00149.

<!-- 
* [**The Conundrum of Success in Music: Playing it or Talking About it?**](https://ieeexplore.ieee.org/document/8815760)
    * 預測即將推出的專輯的Billboard 200表現
    * Methodology
        * Random forest - 表現最佳
        * SVM
        * MLP
    * Data collection
        * iTunes(Apple Music), Spotify 一個月內即將推出的專輯
        * Social medias: **Twitter(X)**, **Billboard News**, New York Times, Instagram, Facebook, YouTube
          用音樂家與歌名作為Query在社群媒體上搜尋(Selenium)，以文章數量、喜歡數、追隨數作為特徵。
          用Vader套件做內容正負面分析
    * Cons: 無法套用在KKCompany競賽
    * [Apple Music API](https://developer.apple.com/documentation/applemusicapi/)
 -->