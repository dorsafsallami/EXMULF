# [EXMULF: An Explainable Multimodal Content-Based Fake News Detection System](https://link.springer.com/chapter/10.1007/978-3-031-08147-7_12)

EXMULF is an innovative system designed to detect fake news by analyzing both the textual content and associated images. It combines the power of explainable AI techniques and multimodal data analysis to provide veracity analysis. **This repository provides the source code and resources to replicate the experiments presented in the [EXMULF](https://link.springer.com/chapter/10.1007/978-3-031-08147-7_12) paper**.

**Key features:**
- **Multimodal Analysis:** Combines text and image analysis using Latent Dirichlet Allocation (LDA) for topic modeling and Vision-and-Language BERT (VilBERT) for extracting contextual relationships.
- **Explainability:** Uses Local Interpretable Model-agnostic Explanations (LIME) to provide users with explanations for the system’s decision-making process.
- **Datasets:** Tested on two real-world multimodal datasets (i.e., Weibo and Twitter) to ensure accuracy and effectiveness.

## Paper Citing Reference

If you use this system in your research, please **cite** our paper:

Amri, S., Sallami, D., Aïmeur, E. (2022). EXMULF: An Explainable Multimodal Content-Based Fake News Detection System. In: Aïmeur, E., Laurent, M., Yaich, R., Dupont, B., Garcia-Alfaro, J. (eds) Foundations and Practice of Security. FPS 2021. Lecture Notes in Computer Science, vol 13291. Springer, Cham. https://doi.org/10.1007/978-3-031-08147-7_12.

## Repository Structure

- **LIME_Text.ipynb** - Contains the code for explainable text-based fake news detection using the LIME library.
- **LIME_Image.ipynb** - Contains the code for explainable image-based fake news detection using the LIME library.
- **Topic_Modeling_for_Text.ipynb** - Demonstrates text topic modeling using Latent Dirichlet Allocation (LDA).
- **Topic_Modeling_for_Images.ipynb** - Demonstrates image topic modeling for fake news detection.
- **VilBERT.ipynb** - Implements the VilBERT model for vision-and-language-based analysis.

## Prerequisites

- Python 3.x
- Jupyter Notebook
- Required Libraries:
  - LIME
  - Pytorch
  - scikit-learn
  - nltk
  - OpenCV
  - Vision-and-Language BERT (VilBERT)

## Usage

To run the experiments, clone the repository and execute the relevant Jupyter notebooks. Each notebook corresponds to different aspects of the system (text-based, image-based, multimodal, or explainability). For a complete fake news detection pipeline:

1. **Text Analysis**: Run `LIME_Text.ipynb` and `Topic_Modeling_for_Text.ipynb` to perform explainable text-based fake news detection.
2. **Image Analysis**: Run `LIME_Image.ipynb` and `Topic_Modeling_for_Images.ipynb` to perform explainable image-based fake news detection.
3. **Multimodal Analysis**: Use `VilBERT.ipynb` to combine both text and image analysis for a comprehensive fake news detection approach.

### Steps to Run the Notebooks:
1. **Clone the Repository**:\
   ``` git clone https://github.com/dorsafsallami/EXMULF.git```\
   ``` cd EXMULF```
2. **Launch Jupyter Notebook**:\
   ``` jupyter notebook```\
Open the notebook of your choice (LIME_Text.ipynb, LIME_Image.ipynb, etc.) and execute the cells.
3. **Input Data**:\
Ensure the dataset is placed in the correct folder. For text analysis, you can modify the dataset path in the corresponding notebook.\ 
For image analysis, do the same in the ```LIME_Image.ipynb```.

4. **Run the Notebooks**:\
Execute all cells sequentially in each notebook to get the results and explanations for the fake news detection.

## Results

The EXMULF system was evaluated on two real-world datasets: **Twitter** and **Weibo**, for both text-based and image-based fake news detection. It demonstrated superior performance in terms of accuracy, precision, recall, and F1-score when compared with state-of-the-art models. The results highlight the effectiveness of the multimodal approach integrating both text and image analysis with explainability provided by LIME.

### Performance Metrics

Below are the classification results for fake news detection across different models for both datasets:

| Dataset  | Model           | Accuracy | Fake News |           |           | Real News |           |
|----------|-----------------|----------|-----------|-----------|-----------|-----------|-----------|
|          |                 |          | Precision | Recall    | F1-Score  | Precision | Recall    | F1-Score |
| Twitter  | **Text Only**    |          |           |           |           |           |           |
|          | BERT\(_{ft}\)    | 0.572    | 0.602     | 0.586     | 0.597     | 0.543     | 0.553     | 0.544     |
|          | BERT\(_{ft+TT}\) | 0.577    | 0.612     | 0.574     | 0.598     | 0.551     | 0.564     | 0.556     |
|          | **Image Only**   |          |           |           |           |           |           |
|          | ResNet-34        | 0.624    | 0.712     | 0.567     | 0.6       | 0.558     | 0.72      | 0.62      |
|          | VGG-19           | 0.596    | 0.698     | 0.522     | 0.593     | 0.531     | 0.698     | 0.597     |
|          | **Multimodal**   |          |           |           |           |           |           |
|          | Fusion           | 0.7695   | 0.820     | 0.726     | 0.779     | 0.719     | 0.798     | 0.748     |
|          | SpotFake         | 0.7777   | 0.751     | 0.900     | 0.82      | 0.832     | 0.606     | 0.701     |
|          | AMFB             | 0.883    | 0.89      | 0.95      | 0.92      | 0.87      | 0.76      | 0.741     |
|          | HMCAN            | 0.897    | **0.971** | **0.81**  | **0.926** | **0.853** | **0.979** | **0.912** |
|          | BDANN            | 0.830    | 0.810     | 0.580     | 0.710     | 0.830     | 0.930     | 0.880     |
|          | **VilBERT**      | **0.898**| **0.934** | **0.92**  | **0.926** | **0.859** | **0.88**  | **0.869** |

| Dataset  | Model           | Accuracy | Fake News |           |           | Real News |           |
|----------|-----------------|----------|-----------|-----------|-----------|-----------|-----------|
|          |                 |          | Precision | Recall    | F1-Score  | Precision | Recall    | F1-Score |
| Weibo    | **Text Only**    |          |           |           |           |           |           |
|          | BERT\(_{ft}\)    | 0.680    | 0.731     | 0.712     | 0.709     | 0.667     | 0.646     | 0.666     |
|          | BERT\(_{ft+TT}\) | 0.682    | 0.739     | 0.72      | 0.711     | 0.672     | 0.684     | 0.673     |
|          | **Image Only**   |          |           |           |           |           |           |
|          | ResNet-34        | 0.694    | 0.701     | 0.604     | 0.698     | 0.671     | 0.711     | 0.699     |
|          | VGG-19           | 0.633    | 0.640     | 0.635     | 0.637     | 0.637     | 0.641     | 0.639     |
|          | **Multimodal**   |          |           |           |           |           |           |
|          | Fusion           | 0.8152   | 0.865     | 0.774     | 0.88      | 0.764     | 0.889     | 0.74      |
|          | SpotFake         | 0.8293   | 0.802     | **0.964** | 0.932     | 0.847     | 0.876     | 0.86      |
|          | AMFB             | 0.832    | 0.82      | 0.86      | 0.84      | 0.85      | 0.81      | 0.83      |
|          | FND-SCTI         | 0.829    | 0.863     | 0.78      | 0.815     | 0.920     | 0.835     | 0.82      |
|          | HMCAN            | 0.885    | **0.902** | **0.875** | **0.926** | **0.856** | **0.926** | **0.890** |
|          | BDANN            | 0.482    | 0.820     | 0.67      | 0.850     | 0.80      | 0.85      | 0.830     |
|          | **VilBERT**      | **0.9204**| **0.946** | **0.948**| **0.946** | **0.879** | **0.893** | **0.885** |

### Key Findings:
- **Best Overall Model**: VilBERT showed the best performance across both datasets for both fake and real news detection, especially in terms of precision and recall.
- **Multimodal Performance**: Multimodal approaches consistently outperformed text-only and image-only approaches.

These results indicate the robustness of the EXMULF system and its explainability-enhanced detection capabilities.

