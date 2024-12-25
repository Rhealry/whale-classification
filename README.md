---
jupyter:
  jupytext:
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.3'
      jupytext_version: 1.16.4
  kernelspec:
    display_name: Python 3 (ipykernel)
    language: python
    name: python3
---

<!-- #region -->
# README: 鲸鱼声音分析与分类项目

## 项目概述
本项目旨在通过分析鲸鱼声音的数据来识别和分类不同的鲸鱼物种。我们使用特征提取、聚类分析和监督学习等机器学习技术，探索并分类鲸鱼的声音模式。本项目的目标是构建一个模型，可以根据鲸鱼的声音特征，对新的音频数据进行物种识别。

## 数据集来源
- **数据集来源**：Watkins Marine Mammal Sound Database
- **数据内容**：数据集包含蓝鲸（Blue Whale）、座头鲸（Humpback Whale）、北太平洋露脊鲸（North Pacific Right Whale）、鳍鲸（Fin Whale）等多种鲸鱼物种的音频记录，每条音频包含鲸鱼的特定叫声和频率信息。
- **文件类型**：WAV 音频文件，每种鲸鱼物种包含多条音频记录
- **采样率**：将所有音频文件加载为 22050 Hz，以确保特征提取的一致性。

## 项目文件
- **主 Notebook 文件**：`whale_sound_classification.ipynb`，包含主要的代码和分析步骤。
- **数据文件**：`whale_sounds.zip`，包含所有鲸鱼音频文件，解压后确保音频文件路径正确链接至 Notebook。
- **模型与分析文件**：Notebook 内的代码用于音频文件的加载、特征提取、聚类、分类和预测。

## 运行说明
1. **依赖安装**：
   运行本 Notebook 需要安装以下 Python 库：
   ```bash
   pip install librosa numpy matplotlib sklearn plotly

## 数据路径设置
将 `audio.zip` 解压到项目根目录，并确保 Notebook 中音频文件路径正确指向解压后的文件。

## Notebook 运行步骤

1. 打开并运行 `Assignment2.ipynb` 文件。
2. 按照 Notebook 中的步骤，加载音频文件、提取特征、进行聚类和分类分析。
3. 根据代码中的提示，调整聚类和分类参数以优化模型的性能。

## 分析流程

### 1. 数据理解
首先加载并初步检查音频数据，确保数据的结构和内容符合分析需求。

### 2. 特征提取与描述性统计
- 使用 `librosa` 提取音频的 **MFCC 特征** 和 **频谱特征**，并计算描述性统计（包括均值、标准差、最小值和最大值）。
- 描述性统计帮助我们初步了解音频特征的分布，便于后续的聚类和分类分析。

### 3. 聚类分析
- **KMeans 聚类**：对音频特征进行聚类，生成伪标签以帮助识别鲸鱼声音模式。
- **异常值检测**：利用聚类结果对异常值进行检测，并清理异常数据以提高分类模型的准确性。

### 4. 推断性统计
- **监督学习分类**：使用聚类生成的伪标签作为目标变量，训练随机森林分类模型。
- **交叉验证**：对模型进行评估，并利用清理后的数据进行分类模型的训练和验证。
- **新数据预测**：使用训练好的模型预测新音频数据的物种类别。

## 结果与讨论

- **聚类结果**：通过聚类分析，不同的鲸鱼音频可以分为多个模式，这些模式可能对应于不同的物种。
- **分类结果**：在交叉验证的评估中，清理后的数据集表现出较高的准确率，表明模型在伪标签生成和分类任务上具有良好的预测能力。


### 目录结构

```plaintext
whale_sound_classification/
├── Assignment2.ipynb   # 主代码文件
├── audio.zip                   # 音频文件压缩包
└── README.md                          # 本说明文件

<!-- #endregion -->

# README: Whale Sound Analysis and Classification Project

## Project Overview
This project aims to analyze whale sound data to identify and classify different whale species. By using feature extraction, clustering analysis, and supervised learning techniques, we explore and categorize various whale sound patterns. The goal is to build a model capable of recognizing whale species from new audio data based on sound features.

## Dataset Source
- **Source**: Watkins Marine Mammal Sound Database
- **Dataset Content**: The dataset includes audio recordings of various whale species such as Blue Whale, Humpback Whale, North Pacific Right Whale, and Fin Whale. Each audio file captures specific whale vocalizations and frequency information.
- **File Type**: WAV audio files, with multiple recordings per whale species.
- **Sampling Rate**: All audio files are loaded at 22050 Hz to ensure consistent feature extraction.

## Project Files
- **Main Notebook**: `whale_sound_classification.ipynb`, containing the primary code and analysis steps.
- **Data Files**: `whale_sounds.zip`, includes all whale audio files. Unzip and ensure the file paths link correctly to the Notebook.
- **Model and Analysis Files**: Code within the Notebook is used to load audio files, extract features, perform clustering, classify, and predict.

## Instructions for Running
1. **Dependencies**:
   Install the required Python libraries by running:
   ```bash
   pip install librosa numpy matplotlib sklearn plotly

## Data Path Setup
Unzip `audio.zip` in the project root directory, and ensure the audio file paths in the Notebook point to the unzipped files.

## Steps for Running the Notebook
1. Open and run the `Assignment2.ipynb` file.
2. Follow the steps in the Notebook to load audio files, extract features, and conduct clustering and classification analyses.
3. Adjust clustering and classification parameters as suggested in the code to optimize model performance.

## Analysis Workflow

### 1. Data Understanding
Load and initially inspect the audio data to ensure its structure and content align with the analysis requirements.

### 2. Feature Extraction and Descriptive Statistics
- Extract **MFCC features** and **spectral features** from the audio using `librosa`, and compute descriptive statistics (mean, standard deviation, minimum, and maximum).
- Descriptive statistics help provide a preliminary understanding of the distribution of audio features, which facilitates clustering and classification.

### 3. Clustering Analysis
- **KMeans Clustering**: Perform clustering on the audio features to generate pseudo-labels that help identify whale sound patterns.
- **Outlier Detection**: Detect outliers based on clustering results and remove these to enhance the accuracy of the classification model.

### 4. Inferential Statistics
- **Supervised Learning Classification**: Use the pseudo-labels generated from clustering as target variables to train a Random Forest classification model.
- **Cross-Validation**: Evaluate the model and use the cleaned data for training and validation.
- **New Data Prediction**: Use the trained model to predict the species label of new audio data.

## Results and Discussion

- **Clustering Results**: Clustering analysis indicates that whale sounds can be grouped into several patterns, potentially corresponding to different species.
- **Classification Results**: In cross-validation, the cleaned dataset achieved high accuracy, suggesting that the model effectively predicts species based on pseudo-labels and classification tasks.

## Directory Structure

```plaintext
whale_sound_classification/
├── Assignment2.ipynb   # Main code file
├── audio.zip                   # Audio files zip package
└── README.md                          # Project documentation file


```python

```
---
jupyter:
  jupytext:
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.3'
      jupytext_version: 1.16.4
  kernelspec:
    display_name: Python 3 (ipykernel)
    language: python
    name: python3
---

<!-- #region -->
# README: 鲸鱼声音分析与分类项目

## 项目概述
本项目旨在通过分析鲸鱼声音的数据来识别和分类不同的鲸鱼物种。我们使用特征提取、聚类分析和监督学习等机器学习技术，探索并分类鲸鱼的声音模式。本项目的目标是构建一个模型，可以根据鲸鱼的声音特征，对新的音频数据进行物种识别。

## 数据集来源
- **数据集来源**：Watkins Marine Mammal Sound Database
- **数据内容**：数据集包含蓝鲸（Blue Whale）、座头鲸（Humpback Whale）、北太平洋露脊鲸（North Pacific Right Whale）、鳍鲸（Fin Whale）等多种鲸鱼物种的音频记录，每条音频包含鲸鱼的特定叫声和频率信息。
- **文件类型**：WAV 音频文件，每种鲸鱼物种包含多条音频记录
- **采样率**：将所有音频文件加载为 22050 Hz，以确保特征提取的一致性。

## 项目文件
- **主 Notebook 文件**：`whale_sound_classification.ipynb`，包含主要的代码和分析步骤。
- **数据文件**：`whale_sounds.zip`，包含所有鲸鱼音频文件，解压后确保音频文件路径正确链接至 Notebook。
- **模型与分析文件**：Notebook 内的代码用于音频文件的加载、特征提取、聚类、分类和预测。

## 运行说明
1. **依赖安装**：
   运行本 Notebook 需要安装以下 Python 库：
   ```bash
   pip install librosa numpy matplotlib sklearn plotly

## 数据路径设置
将 `audio.zip` 解压到项目根目录，并确保 Notebook 中音频文件路径正确指向解压后的文件。

## Notebook 运行步骤

1. 打开并运行 `Assignment2.ipynb` 文件。
2. 按照 Notebook 中的步骤，加载音频文件、提取特征、进行聚类和分类分析。
3. 根据代码中的提示，调整聚类和分类参数以优化模型的性能。

## 分析流程

### 1. 数据理解
首先加载并初步检查音频数据，确保数据的结构和内容符合分析需求。

### 2. 特征提取与描述性统计
- 使用 `librosa` 提取音频的 **MFCC 特征** 和 **频谱特征**，并计算描述性统计（包括均值、标准差、最小值和最大值）。
- 描述性统计帮助我们初步了解音频特征的分布，便于后续的聚类和分类分析。

### 3. 聚类分析
- **KMeans 聚类**：对音频特征进行聚类，生成伪标签以帮助识别鲸鱼声音模式。
- **异常值检测**：利用聚类结果对异常值进行检测，并清理异常数据以提高分类模型的准确性。

### 4. 推断性统计
- **监督学习分类**：使用聚类生成的伪标签作为目标变量，训练随机森林分类模型。
- **交叉验证**：对模型进行评估，并利用清理后的数据进行分类模型的训练和验证。
- **新数据预测**：使用训练好的模型预测新音频数据的物种类别。

## 结果与讨论

- **聚类结果**：通过聚类分析，不同的鲸鱼音频可以分为多个模式，这些模式可能对应于不同的物种。
- **分类结果**：在交叉验证的评估中，清理后的数据集表现出较高的准确率，表明模型在伪标签生成和分类任务上具有良好的预测能力。


### 目录结构

```plaintext
whale_sound_classification/
├── Assignment2.ipynb   # 主代码文件
├── audio.zip                   # 音频文件压缩包
└── README.md                          # 本说明文件

<!-- #endregion -->

# README: Whale Sound Analysis and Classification Project

## Project Overview
This project aims to analyze whale sound data to identify and classify different whale species. By using feature extraction, clustering analysis, and supervised learning techniques, we explore and categorize various whale sound patterns. The goal is to build a model capable of recognizing whale species from new audio data based on sound features.

## Dataset Source
- **Source**: Watkins Marine Mammal Sound Database
- **Dataset Content**: The dataset includes audio recordings of various whale species such as Blue Whale, Humpback Whale, North Pacific Right Whale, and Fin Whale. Each audio file captures specific whale vocalizations and frequency information.
- **File Type**: WAV audio files, with multiple recordings per whale species.
- **Sampling Rate**: All audio files are loaded at 22050 Hz to ensure consistent feature extraction.

## Project Files
- **Main Notebook**: `whale_sound_classification.ipynb`, containing the primary code and analysis steps.
- **Data Files**: `whale_sounds.zip`, includes all whale audio files. Unzip and ensure the file paths link correctly to the Notebook.
- **Model and Analysis Files**: Code within the Notebook is used to load audio files, extract features, perform clustering, classify, and predict.

## Instructions for Running
1. **Dependencies**:
   Install the required Python libraries by running:
   ```bash
   pip install librosa numpy matplotlib sklearn plotly

## Data Path Setup
Unzip `audio.zip` in the project root directory, and ensure the audio file paths in the Notebook point to the unzipped files.

## Steps for Running the Notebook
1. Open and run the `Assignment2.ipynb` file.
2. Follow the steps in the Notebook to load audio files, extract features, and conduct clustering and classification analyses.
3. Adjust clustering and classification parameters as suggested in the code to optimize model performance.

## Analysis Workflow

### 1. Data Understanding
Load and initially inspect the audio data to ensure its structure and content align with the analysis requirements.

### 2. Feature Extraction and Descriptive Statistics
- Extract **MFCC features** and **spectral features** from the audio using `librosa`, and compute descriptive statistics (mean, standard deviation, minimum, and maximum).
- Descriptive statistics help provide a preliminary understanding of the distribution of audio features, which facilitates clustering and classification.

### 3. Clustering Analysis
- **KMeans Clustering**: Perform clustering on the audio features to generate pseudo-labels that help identify whale sound patterns.
- **Outlier Detection**: Detect outliers based on clustering results and remove these to enhance the accuracy of the classification model.

### 4. Inferential Statistics
- **Supervised Learning Classification**: Use the pseudo-labels generated from clustering as target variables to train a Random Forest classification model.
- **Cross-Validation**: Evaluate the model and use the cleaned data for training and validation.
- **New Data Prediction**: Use the trained model to predict the species label of new audio data.

## Results and Discussion

- **Clustering Results**: Clustering analysis indicates that whale sounds can be grouped into several patterns, potentially corresponding to different species.
- **Classification Results**: In cross-validation, the cleaned dataset achieved high accuracy, suggesting that the model effectively predicts species based on pseudo-labels and classification tasks.

## Directory Structure

```plaintext
whale_sound_classification/
├── Assignment2.ipynb   # Main code file
├── audio.zip                   # Audio files zip package
└── README.md                          # Project documentation file


```python

```
