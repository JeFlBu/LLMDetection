# LLM Usage Detection in Emails

## Simple Detection

This repository contains scripts and notebooks for detecting the usage of Large Language Models (LLMs) in emails. We employ two models for detection:

1. **SuperAnnotate/roberta-large-llm-content-detector**
2. **[Binoculars](https://arxiv.org/abs/2401.12070)**

### Notebooks

- `build_scores.ipynb`: Computes LLM detection scores using the **SuperAnnotate** model.
- `build_scores_binocular.ipynb`: Computes LLM detection scores using the **Binoculars** model.

Please contact us to obtain the **Parquet files** containing the emails used for detection.

### Granularity Levels

We define three levels of granularity for LLM detection in emails:

- **Email level**
- **Paragraph level**
- **Sentence level**

### Visualizations

We provide **PNG files** in the repository, displaying the detection scores obtained using different criteria.

---

## Fine-Tuning

We further fine-tune the **SuperAnnotate** model on generated data to specialize it for email detection.

### Folder Structure

- `newdata/`: Contains code, data, and results related to fine-tuning.
- `generate_mails_with_gpt.ipynb`: Generates a synthetic dataset of emails.
- `further_finetuning_with_emails.ipynb`: Fine-tunes the model using generated emails.
- `build_scores.ipynb`: Generates scores and plots after fine-tuning.

### Data Generation Strategies

We use pre-ChatGPT era emails as **ground truth** for human-written emails and generate new emails using GPT. These generated emails are labeled as **GPT-written**. The strategies used for generation are:

1. **Rewrite**: Rephrase an existing human email.
2. **Merge**: Merge several human-written emails into one.
3. **Generate**: Create an email from scratch based on a detected topic.

We then fine-tune the model using emails generated through one or multiple strategies mentioned above.

### Results

Detection scores and plots are generated using `build_scores.ipynb`. Each plot is saved in a folder named **'strategy_'** followed by the names of the generation techniques used.

---

## Contact

For access to the dataset or further inquiries, please contact us.

