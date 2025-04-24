# DL_Report1
Deep Learning assignment including Dynamic Convolution Module and Two-Layer Network for Image Classification on ImageNet-mini.
flowchart TD
    subgraph 資料準備
      A1[讀取 train.txt (RGB)] --> A2[讀取 val.txt (RGB)]
      A1 --> A3[讀取 test.txt (多通道)]
    end

    subgraph DynamicConv 訓練
      B0[選定超參 (hidden_dim, out_ch)]
      B1[初始化 DynamicConv + ToyClassifier]
      B2[訓練：只用 RGB 訓練集]
      B3[每 epoch → 前向 & 反向傳播，更新權重]
      B4[驗證：計算 val_acc on val.txt]
      B5[調整超參，選出最佳組合]
    end

    subgraph 多通道推論
      C1[固定訓練後模型]
      C2[對 channel_combos = ["RGB","RG","RB","GB","R","G","B"]]
      C3[築測試 DataLoader (對應 combo)]
      C4[計算 Test Accuracy]
      C5[量測 FLOPs & Params]
      C6[儲存至 flexible_dynamicconv_result.csv]
    end

    subgraph StaticBaseline 實驗
      D1[初始化 StaticConvNet (3→64→num_classes)]
      D2[訓練：只用 RGB 訓練集]
      D3[每 epoch → 前向 & 反向傳播，更新權重]
      D4[驗證：計算 val_acc on val.txt]
      D5[測試：計算 test_acc on test.txt]
      D6[量測 FLOPs & Params]
      D7[儲存到同一結果表]
    end

    %% 連線
    A1 & A2 & A3 --> B1
    B1 --> B2 --> B3 --> B4 --> B5
    B5 --> C1 --> C2 --> C3 --> C4 --> C5 --> C6
    A1 & A2 & A3 --> D1
    D1 --> D2 --> D3 --> D4 --> D5 --> D6 --> D7
