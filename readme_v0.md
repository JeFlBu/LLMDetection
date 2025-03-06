# Simple detection

The build_scores.ipynb and build_scores_binocular.ipynb files serve respectively to build score of detection of LLM usage using two models. Respectively "SuperAnnotate/roberta-large-llm-content-detector" and [binoculars](https://arxiv.org/abs/2401.12070)

Please contact us to obtain the parquet files used containing emails.

We set 3 granularity for LLM detection in emails : email, paragraph, sentence

We leave in the repository png displaying scores of detections obtained using different criteria

# Fine tuning

We further fine tune the SuperAnnotate model on data that we generated to specialize the model into detection for emails.

The results and code are in the folder newdata

In this folder, we provide code to create a synthetic dataset in generate_mails_with_gpt.ipynb

We use pre-chatGPT era emails as ground truth for human written emails, and generate new emails with GPT - that are of course labeled as GPT written emails.

The strategies are :

 - rewrite : rephrase a human email

 - merge : merge several human email

 - generate : generate a mail from scratch using a topic. Topics are detected from existing emails

further_finetuning_with_emails permit to fine tune the model using as train data emails geenrated with one or multiple strategies of the one mentioned above

We then use build_scores.ipynb to generate scores and plots. Each of this plot can be found in their respective folder starting with 'strategy' + names of the generation techniques used
