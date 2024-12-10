# Sentiment Analysis Model

This project contains files and resources related to the **Semper8** model, which is used for sentiment analysis. The model is fine-tuned to classify financial text into three sentiment categories: **negative**, **neutral**, and **positive**.

## Large File Location

The `model.safetensors` file and its associated files are too large to be uploaded directly to GitHub. You can download them from the following Google Drive link:

[Download model.safetensors and associated files from Google Drive](https://drive.google.com/drive/folders/11BHnyKy0l9Yt0ml0ZNL6L1HZaGsf4PwR?usp=drive_link)

## Available Files:

- `model.safetensors` (4,27,697 KB)
- `config.json` (1 KB)
- `special_tokens_map.json` (1 KB)
- `tokenizer.json` (695 KB)
- `tokenizer_config.json` (2 KB)
- `vocab.txt` (227 KB)

## Project Overview

The **Semper8** model takes text as input (e.g., news headlines, sentences) and classifies it into one of the three sentiment categories. This model is particularly useful for analyzing financial news, social media sentiment, product reviews, and more.

### Model Features:
- Fine-tuned model for sentiment analysis on financial text.
- Three sentiment categories:
  - **negative**: Indicates a negative sentiment.
  - **neutral**: Indicates neutral sentiment.
  - **positive**: Indicates a positive sentiment.

### Technologies Used:
- **Hugging Face Transformers**: For loading pre-trained models and fine-tuning.
- **PyTorch**: Backend framework for training the model.
- **Python**: The primary language used for development.

## Getting Started

### Prerequisites

- Python 3.7 or later
- Hugging Face's transformers library
- PyTorch (or TensorFlow if preferred)
- Git for version control


## Cloning the Repository


Clone this repository to your local machine:

git clone https://github.com/pai24rohit/semper8project.git

cd semper8project

## Running the Model

Ensure that the sentiment_model folder contains the necessary files: config.json, tokenizer.json, pytorch_model.bin, etc.

Run the sentiment analysis script by creating a new Python script or using the following code to test the sentiment analysis:

from transformers import pipeline

### Load the fine-tuned model
sentiment_analyzer = pipeline("text-classification", model="./sentiment_model", tokenizer="./sentiment_model")

### Test with a news headline
news_headline = "Global markets rally as inflation fears fade."
result = sentiment_analyzer(news_headline)

### Print the sentiment label and confidence score
print(f"Sentiment: {result[0]['label']}")
print(f"Confidence score: {result[0]['score']:.2f}")

### Example Output:

Sentiment: positive

Confidence score: 0.71

## Sentiment Labels:

- negative: Represents a negative sentiment.
- 
- neutral: Represents neutral sentiment (neither positive nor negative).
- 
- positive: Represents a positive sentiment.

## Interpreting the Output:

The model will return the predicted sentiment (LABEL_0, LABEL_1, LABEL_2) as negative, neutral, or positive, based on the confidence score.

## Saving and Loading the Model


You can save the trained model and tokenizer with the following code:

model.save_pretrained("./sentiment_model")

tokenizer.save_pretrained("./sentiment_model")

To load the model and tokenizer:

from transformers import pipeline

sentiment_analyzer = pipeline("text-classification", model="./sentiment_model", tokenizer="./sentiment_model")

## Contributing

If you'd like to contribute to this project, feel free to fork the repository and submit pull requests. Make sure to follow these steps:

- Fork the repository
- Clone your fork to your local machine
- Create a new branch (git checkout -b feature-branch)
- Make your changes and commit them (git commit -am 'Add new feature')
- Push to your fork (git push origin feature-branch)
- Create a pull request

## License

This project is licensed under the MIT License - see the [LICENSE](https://opensource.org/licenses/MIT) file for details.

## Acknowledgements

- Hugging Face for providing the transformers library and pre-trained models.
- The Financial PhraseBank dataset for training the model.
