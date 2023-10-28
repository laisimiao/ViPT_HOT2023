# ViPT_HOT2023
ViPT variants for Hyperspectral Object Tracking Challenge 2023 (https://www.hsitracking.com/)  
  
:trophy: Without bells and whistles, we won **the third place** using single model of ViPT variant.

[Models & Raw Results](https://drive.google.com/drive/folders/1t8ZiPa7FVADhOA0cs0uWcQM-2hGZzRH3?usp=drive_link)
(Google Driver)

## Usage
### Installation
Create and activate a conda environment:
```

```

### Data Preparation
Download the validation and ranking datasets from [official project](https://www.hsitracking.com/contest/). It should look like:
```
$<PATH_of_Data>
-- validation
    -- DepthTrackTraining
        |-- adapter02_indoor
        |-- bag03_indoor
        |-- bag04_indoor
        ...
    -- LasHeR/train/trainingset
        |-- 1boygo
        |-- 1handsth
        ...
    -- VisEvent/train
        |-- 00142_tank_outdoor2
        |-- 00143_tank_outdoor2
        ...
        |-- trainlist.txt
-- ranking
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
```
cd <PATH_of_ViPT_HOT2023/tracking>
```
