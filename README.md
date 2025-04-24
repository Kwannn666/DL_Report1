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

Launch JupyterLab or Jupyter Notebook and open TaskA_All_in_One.ipynb.

Adjust Dataset Path
In the notebook you’ll find:

img_dir = "PATH"

Change it to your local path, for example:

img_dir = "./image"

Execute Cells in Order

Cell 0: Import all required libraries

Cell 1: Define get_channel_mask, Dataset class, DynamicConv, ToyClassifier, StaticConvNet, and evaluation functions

Cell 2: Helper functions (evaluate_baseline, evaluate)

Cell 3: run_baseline and run_flexible_dynamicconv_combinations implementations

Cell 4: Set transform, hyper_configs, then call run_flexible_dynamicconv_combinations and run_baseline, finally merge results and save CSV

Inspect Results
After execution completes, two CSV files will be generated in your working directory:

flexible_dynamicconv_result.csv

final_comparison_result.csv
You can view them directly in the notebook via print(df_all) or open with Excel/Google Sheets.
