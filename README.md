# TSM-R1


# TSM-R1: An Application Architecture of Community-based Intelligent Dialogue Systems for Enhancing Emotional Well-being in Elderly Populations

## Abstract

This study presents the TSM-R1 framework, a three-stage computational architecture designed for elderly emotional well-being in community-based intelligent dialogue systems. The framework integrates Dynamic Time Warping (DTW) for circadian pattern analysis, a Hybrid Attention-Guided Fusion (MAG) module for cross-modal feature alignment, and Domain-Adaptive Training Strategies (DATS) for adaptive service optimization. Through experimental validation on four public datasets and across 15 urban communities, the proposed model demonstrates improvements in emotional state detection, activity prediction, and fall prevention in elderly populations. The system's biological alignment with seniors' circadian rhythms and its technical innovations in multimodal data fusion present a new approach to elderly care AI systems.

## Key Innovations

* **DTW-based Temporal Module**: Captures seniors' daily activity patterns, improving circadian rhythm alignment and predictive accuracy.
* **Hybrid Attention Fusion (MAG)**: Integrates multimodal data with attention-based mechanisms to enhance feature correlation and reduce latency.
* **Domain-Adaptive Training Strategies (DATS)**: Adapts the system to handle cross-age group variations and personalize care recommendations.
* **Real-time Performance**: Achieves a 62% accident reduction with a 0.3s emergency response time.

## Datasets

The data used in this study is publicly available from the following sources:

* **EmpatheticDialogues Dataset**: A collection of 25,000 rounds of dyadic conversations with 32 emotional labels, providing a foundation for modeling elderly emotional interactions. [Link to Dataset](https://github.com/facebookresearch/EmpatheticDialogues)
* **DailyDialog Dataset**: Contains 13,118 multi-turn conversations across 10 domains with emotional intensity annotations. [Link to Dataset](http://yanran.li/dailydialog)
* **EmotionLines Dataset**: Comprises two subsets — Friends (TV sitcom scripts) and EmotionPush (social media chats) — containing 29,245 utterances with emotional transitions. [Link to Dataset](https://doraemon.iis.sinica.edu.tw/emotionlines/download.html)
* **CDial-GPT Dataset**: A Chinese dialogue corpus with 12 million conversation turns, validating model generalizability across cultural contexts. [Link to Dataset](https://github.com/thu-coai/CDial-GPT)

## Installation

### Prerequisites

* Python 3.10 or higher
* PyTorch 2.1
* CUDA 11.8 (for GPU acceleration)

### Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/TSM-R1.git
   cd TSM-R1
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Download the datasets and place them in the appropriate directories. Follow the links above to access and download the datasets.

### Running the Code

To run the model, execute the following command:

```bash
python run_model.py --dataset EmpatheticDialogues --epochs 100 --batch_size 32
```

This will start the training process using the EmpatheticDialogues dataset. You can replace the dataset with any of the datasets mentioned earlier.

### Evaluation

To evaluate the model's performance on a specific dataset, use the following command:

```bash
python evaluate_model.py --dataset EmpatheticDialogues --checkpoint checkpoints/model_best.pth
```

This will load the best model from the checkpoint and evaluate it on the selected dataset.

## Evaluation Metrics

The model's performance is evaluated using three domain-specific metrics:

1. **Health F1-Score (H-F1)**: Balances diagnostic precision and recall for health-related tasks.
2. **Phase Alignment Accuracy (PAA)**: Measures the temporal alignment of predicted biological phases with ground truth.
3. **System Latency (SL)**: Evaluates the end-to-end processing delay per request, including computation and output delivery.

## Results

### Comparative Performance

| Model          | Health F1 | Phase Acc. (%) | SL (ms) |
| -------------- | --------- | -------------- | ------- |
| Our Model      | 0.921     | 89.7           | 320     |
| CUREGraph      | 0.876     | 82.1           | 680     |
| LF-Transformer | 0.812     | 75.3           | 420     |
| EF-LSTM        | 0.784     | 68.9           | 550     |

### Ablation Study

| Configuration | Health F1 | TAR (%) | SL (ms) |
| ------------- | --------- | ------- | ------- |
| Full Model    | 0.923     | 89.1    | 320     |
| w/o DTW       | 0.841     | 72.3    | 310     |
| w/o MAG       | 0.865     | 81.2    | 680     |
| w/o DATS      | 0.902     | 83.7    | 295     |

## Conclusion

This study introduces the TSM-R1 framework, which leverages multimodal data and advanced AI techniques to enhance elderly care systems. The model demonstrates significant improvements in emotional well-being support and activity prediction for seniors, setting a new standard for AI in elderly care.

## Future Work

Future research will address the limitations in demographic representation and enhance the model's ability to handle cross-cultural and cross-socioeconomic variability. Additionally, privacy-preserving alternatives like federated learning will be explored for data protection in real-time applications.
