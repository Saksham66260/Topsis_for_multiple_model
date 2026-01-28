# TOPSIS-based Selection of Best Pre-trained Text Generation Model

**Author:** Saksham Singh 
**Roll No:** 102303157  

---

## **Objective**
The objective of this assignment is to **evaluate and rank pre-trained text generation models** from Hugging Face using **TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)** based on multiple performance criteria, such as:

- **Perplexity**: Lower is better, measures prediction quality.
- **Inference Time**: Lower is better, measures generation speed.
- **Model Size**: Lower is better, memory efficiency.
- **ROUGE Score**: Higher is better, measures quality of generated text.

The goal is to identify the **best model** for text generation using a multi-criteria decision-making approach.

---

## **Steps Followed**

1. **Select Models**: Chose multiple Hugging Face text generation models (`gpt2`, `distilgpt2`, `gpt-neo-125M`).

2. **Generate Text**: Used the same prompt for all models to generate output text.

3. **Compute Metrics**:
    - **Perplexity**: Approximate cross-entropy loss on the prompt.
    - **Inference Time**: Time taken to generate text.
    - **Model Size**: Calculated from model parameters.
    - **ROUGE-L Score**: Measures similarity between prompt and generated text.

4. **Apply TOPSIS**:
    - Normalized the decision matrix.
    - Weighted criteria based on importance.
    - Calculated ideal best and worst solutions.
    - Computed distances from ideal solutions.
    - Calculated TOPSIS score and rank for each model.

5. **Visualize Results**:
    - Created a bar plot of TOPSIS scores to identify the best model.

6. **Save Results**:
    - Saved the TOPSIS ranking to `topsis_huggingface_results.csv`.
    - Saved the plot as `topsis_huggingface_plot.png`.

---

## **Results**

| Model                   | Perplexity | InferenceTime (s) | ModelSize (MB) | ROUGE Score | TOPSIS Score | Rank |
|-------------------------|------------|-----------------|----------------|-------------|--------------|------|
| gpt2                    | 35.79      | 2.69            | 474.70         | 0.26        | 0.41         | 3    |
| distilgpt2              | 68.23      | 1.68            | 312.47         | 0.64        | 0.55         | 1    |
| EleutherAI/gpt-neo-125M | 30.38      | 2.33            | 477.59         | 0.26        | 0.46         | 2    |

---

## **Graphs**

![TOPSIS Scores](./topsis_huggingface_plot%20(1).png)


The bar plot above shows the **TOPSIS score for each model**, where a higher score indicates a better model based on the selected criteria.

---

## **Conclusion**

- Using **TOPSIS**, we can effectively rank text generation models based on multiple performance metrics.
- In this evaluation, **`distilgpt2`** achieved the **highest TOPSIS score**, making it the best model for the given prompt considering quality, speed, and size.
- This approach provides a **systematic and objective method** for model selection rather than relying on a single metric.


