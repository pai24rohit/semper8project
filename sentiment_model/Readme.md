# Semper8Project

This project contains files and resources related to the **Semper8** model, which is used for [brief description of model's purpose or functionality]. Since some of the files are too large to store directly in this GitHub repository, they have been uploaded to Google Drive for easy access.

## Large File Location

The `model.safetensors` file and its associated files are too large to be uploaded directly to GitHub. You can download them from the following Google Drive link:

[Download model.safetensors and associated files from Google Drive](https://drive.google.com/drive/folders/11BHnyKy0l9Yt0ml0ZNL6L1HZaGsf4PwR?usp=drive_link)

### Available Files:
- `model.safetensors` (4,27,697 KB)
- `config.json` (1 KB)
- `special_tokens_map.json` (1 KB)
- `tokenizer.json` (695 KB)
- `tokenizer_config.json` (2 KB)
- `vocab.txt` (227 KB)

## Requirements

To get started with this project, you will need the following dependencies:

- Python 3.x
- [Git](https://git-scm.com/)
- [Git Large File Storage (LFS)](https://git-lfs.github.com/) (for managing large files)
- [Hugging Face Transformers](https://huggingface.co/transformers/)
- Any other dependencies your project requires.

# Sentiment Analysis Model

This project uses a fine-tuned sentiment analysis model for classifying text into three categories: **positive**, **neutral**, and **negative**.

## Sentiment Labels:
- **negative**: Represents a negative sentiment.
- **neutral**: Represents a neutral sentiment with no clear positive or negative stance.
- **positive**: Represents a positive sentiment.

## Model Inputs:
The model takes in a text string as input (e.g., a news headline or a sentence).

## Model Outputs:
The output consists of:
1. **Sentiment Label**: One of the following: `negative`, `neutral`, `positive`.
2. **Confidence Score**: The model's confidence in the prediction, ranging from 0 to 1.

### Example:
```python
from transformers import pipeline

# Load the fine-tuned model
sentiment_analyzer = pipeline("text-classification", model="./sentiment_model", tokenizer="./sentiment_model")

# Test with a news headline
news_headline = "Global markets rally as inflation fears fade."
result = sentiment_analyzer(news_headline)

# Print the sentiment label and confidence score
print(f"Sentiment: {result[0]['label']}")
print(f"Confidence score: {result[0]['score']:.2f}")
