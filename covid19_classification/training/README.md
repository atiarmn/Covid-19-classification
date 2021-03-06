# Training

you can train your own **U-Net** or **Residual U-Net** here by run `training.py` file.

# Parser

    python training.py -h
| small flag  |  flag     | Description     |
| :----:      |    :----: |     :---:      |
|-h| --help|            show this help message and exit|
|-p | --path|           Path to dataset [../training/data/COVID-19_Radiography_Dataset]|
|-pr| --preprocess |            Select Pre-Process|
|-N | --network|      Select Model['efficientnet', 'mobilenet']|
|-su| --summary       |     Print model summary|
|-bs| --batch_size     |    batch_size|
|-e| --epochs          |   Number of epochs|
|-H | --history   |  Show history|
|-ML | --mlflow| Save Models with MLFlow|
|-S | --save| Save Model|
|-mn | --modelName| Model Name for Saving|
|-W | --weights| Save Model's weights|

-----------------------------------------------------------------
### for example:

    python3 training.py -p ../training/data/train -pr -N mobilenet --summary -bs 8 -e 2 -H --mlflow -S -mn local_save

use images in data directory as dataset, and `MobileNetV2` as model w/ *batch_size* = 8 & 2 _epochs_.
print a **summary** of model and plot model's _history_ and save records with **mlflow**. after that save model as `local_save.h5` in weights folder.

-----------------------------------------------------------------------
**Note** : if you select mlflow, training resualts will save in `mlruns` folder.

To see mlflow resualts copy and paste following command in your terminal:

    mlflow ui
