# Self-Prompting Analogical Reasoning for UAV Object Detection
The repo is the official implementation of SPAR-YOLOv8.

Paper:[Self-Prompting Analogical Reasoning for UAV Object Detection](https://ojs.aaai.org/index.php/AAAI/article/view/34026/36181)

## Environment setup
Our work is based on the integrated YOLOv8 library ([https://github.com/ultralytics/ultralytics](https://github.com/ultralytics/ultralytics)).  
Therefore, the environment setup is the same. You can install the required dependencies with the following commands:

`pip install ultralytics`

`pip install torch-geometric`

## Dataset

Our experiments are conducted on two benchmarks: **VisDrone** and **UAVDT**.  
We would like to thank [UFPMP](https://github.com/PuAnysh/UFPMP-Det) for providing the dataset download links:

- **VisDrone**: [Download Link](https://pan.baidu.com/s/1FfAsAApHZruucO5A2QgQAg) (Extraction Code: `qrvs`)
- **UAVDT**: [Download Link](https://pan.baidu.com/s/1KLmU5BBWwgtFbuZa7QWavw) (Extraction Code: `z08x`)

## Local Run
To run the code locally, the following modifications are required:

- In `Analogical/ultralytics/utils/dist.py`, change the address in **line 52** to the path where your project is located.
- Then, modify the file paths in `train.py`, `val.py`, and `predict.py` accordingly for training, validation, and inference, respectively.

## Code Structure

The main implementation of the code in the paper is located in the following files:

- **learnable prompt** and **text-visual attention** are implemented in `Analogical/ultralytics/nn/tasks.py`.
- The **AnaC2f module** and **ImagePoolingAttn module** in `Analogical/ultralytics/nn/modules/block.py` implement cross-learning between text and vision, score map generation, as well as **Analogical reasoning** functionality.

We sincerely appreciate your interest in our work. Your support and attention are invaluable to us. We hope that our research can contribute to the field, and we welcome any feedback or suggestions you may have.
