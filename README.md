# ViPT_HOT2023
ViPT variants for Hyperspectral Object Tracking Challenge 2023 (https://www.hsitracking.com/)  
  
:trophy: Without bells and whistles, we won **the third place** using single model of ViPT variant.

[Models & Raw Results](https://drive.google.com/drive/folders/1t8ZiPa7FVADhOA0cs0uWcQM-2hGZzRH3?usp=drive_link)
(Google Driver)  [Video Presentation](https://youtu.be/BfxQ6rIxjvU)(YouTube)

## Usage
### Installation
Create and activate a conda environment, we've tested on this env:
```
timm                    0.6.11
torch                   1.9.1+cu102
torchfile               0.1.0
torchvision             0.10.1+cu102
python                  3.7.10
```

### Data Preparation
Download the validation and ranking datasets from [official project](https://www.hsitracking.com/contest/). It should look like:
```
$<PATH_of_Data>
-- validation
    -- HSI-NIR
        |-- basketball3
        ...
    -- HSI-NIR-FalseColor
        |-- basketball3
        ...
    -- HSI-RedNIR
        |-- ball&mirror9
        ...
    -- HSI-RedNIR-FalseColor
        |-- ball&mirror9
        ...
    -- HSI-VIS
        |-- ball
        ...
    -- HSI-VIS-FalseColor
        |-- ball
        ...
-- ranking
    -- HSI-NIR
        |-- basketball2
        ...
    -- HSI-NIR-FalseColor
        |-- basketball2
        ...
    -- HSI-RedNIR
        |-- backpack4
        ...
    -- HSI-RedNIR-FalseColor
        |-- backpack4
        ...
    -- HSI-VIS
        |-- cards6
        ...
    -- HSI-VIS-FalseColor
        |-- cards6
        ...
```

### Path Setting
Run the following command to set paths:
```
cd <PATH_of_ViPT_HOT2023>
python tracking/create_default_local_file.py --workspace_dir . --data_dir ./data --save_dir ./output
```
You can also modify paths by these two files:
```
./lib/train/admin/local.py  # paths for training
./lib/test/evaluation/local.py  # paths for testing
```

### Testing
- Download pretrained model `ViPT_all.pth.tar` from [link](https://drive.google.com/drive/folders/1t8ZiPa7FVADhOA0cs0uWcQM-2hGZzRH3?usp=drive_link) and put it into dir `final_model`.
- Modify the **line177** and **line184** of the file `tracking/test_hsi_mgpus_all.py` to yours.
```
cd <PATH_of_ViPT_HOT2023/tracking>
python test_hsi_mgpus_all.py --dataset_name HOT23VAL
python test_hsi_mgpus_all.py --dataset_name HOT23TEST
```
