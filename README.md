# Introduction to Data Science Final Project - Music Popularity Prediction

### Group 21

* 李姿慧@zephyrxin01  
* 林祥順@lin157644

## Introduction

&emsp;&emsp;當今音樂串流平台的普及促使人們更傾向使用串流服務聆聽音樂。這種趨勢不僅節省成本，也更加便捷。以Spotify為例。透過預測歌曲流行程度，我們可以協助音樂家決定歌曲上架與廣告策略，同時為串流平台提供熱門音樂推薦的重要參考依據。  
&emsp;&emsp;我們預計透過音樂串流平台提供的開放API，獲取歌曲相關資訊，包括作者、專輯、年份和風格等，以及利用預覽片段和外部資料集輔助，量化音樂特徵，例如歌唱比例、音調和動態範圍等，以達成預測歌曲流行程度的目標。

## Dataset

* [**Kaggle: Spotify Tracks Dataset**](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset)
    * 125種不同流派
    * \> 11000 筆歌曲資料
    * 包含預先量化的音訊特徵
* [**Spotify API**](https://developer.spotify.com/documentation/web-api/reference/get-track)
    * `https://api.spotify.com/v1/tracks/{id}`
      `preview_url` : A link to a 30 second preview (MP3 format) of the track.

## Installation

Intall the required packages with anaconda

```
conda env create -f environment.yml --prefix data-science-project
```

Activate the environment

```
conda activate data-science-project
```

<!-- [^xxx]: XXX: [**Source**](https://github.com/) - [**arXiv:xxx**](https://arxiv.org/abs/xxx) -->