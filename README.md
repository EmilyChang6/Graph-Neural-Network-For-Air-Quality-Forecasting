# Graph-Neural-Network-For-Air-Quality-Forecasting
本研究將基於 GNN 的分支模型圖卷積神經網路(Graph Convolution Network,GCN)，結合長短期記憶(Long Short-Term Memory, LSTM) 之架構建立模型，針對臺南市空氣品質指標(Air Quality Index, AQI)，利用前 4 小時的數據，來预测未來 3 小時的 AQI，並與單一 LSTM 模型進行比較。

## 研究方法
### (一) 數據集
* 採用行政院環境保護署所提供之空氣品質指標(AQI)(歷史資料)及縣市(臺南市)小時值資料集 (從 2021 年 10 月 1 日到 2022 年 9 月 30 日)
* 臺南市: 4 個測站，分別為新營、善化、安南、臺南 
* 依季風劃分，以月份分割時序列數據為 2 個資料集，分別進行模型訓練 (考量到在東北季風和西南季風期間的 AQI 趨勢變動過大，可能會造成模型學習之成效)
* 訓練集 2937 筆，驗證集367 筆，測試集 368 筆資料
### (二) 模型架構
本研究使用 GNN 的分支模型 GCN，結合 LSTM 之架構建立模型。利用 GCN 提取測站間的空間特徵，再使用 LSTM 演算法提取時間特徵，最後由全連接層來綜合時空特徵，產生 AQI 的預測結果。  
<img src="https://github.com/EmilyChang6/Graph-Neural-Network-For-Air-Quality-Forecasting/blob/main/model.PNG" width="500">

### (三) 預測結果
<img src="https://github.com/EmilyChang6/Graph-Neural-Network-For-Air-Quality-Forecasting/blob/main/results.png" width="800">
