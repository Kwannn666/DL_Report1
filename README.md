# DL_Report1
Deep Learning assignment including Dynamic Convolution Module and Two-Layer Network for Image Classification on ImageNet-mini.

Task_A 

## How to Run

1. **Environment Setup**  
   - Python ≥ 3.8  
   - Install required packages:  
     ```bash
     pip install torch torchvision pillow pandas tqdm thop
     ```

2. **Download and Extract Dataset**  
   ```bash
   wget https://cchsu.info/files/images.zip -O images.zip
   unzip images.zip -d image
Ensure that train.txt, val.txt, test.txt and the image files are all under the ./image directory.

Open the Notebook

Launch JupyterLab or Jupyter Notebook and open Task1.ipynb.

Adjust Dataset Path
In the notebook you’ll find:

img_dir = "YOUR_PATH"

Change it to your local path, for example:

img_dir = "./image"

DL_Report1
├──Task1/
   └──Task1.ipynb
   ├── flexible_dynamicconv_result.csv
   └── final_comparison_result.csv
└──image/
   └──images/
      ├── train.txt
      ├── val.txt
      ├──test.txt
      └──image/
         └──n02111277
               ...
               
Execute Cells in Order

Cell 1: 載入套件

Cell 2: 自定義通道選擇設定

Cell 3: 資料集設定

Cell 4: 動態捲積

Cell 5: 分類器

Cell 6: Baseline CNN

Cell 7: 評估函數

Cell 8: 程式主流程

Cell 9: 執行程式

Inspect Results
After execution completes, two CSV files will be generated in your working directory:

flexible_dynamicconv_result.csv

final_comparison_result.csv

You can view them directly in the notebook via print(df_all) or open with Excel/Google Sheets.
