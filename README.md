# Next Word Prediction using LSTM

This project is a simple **next-word prediction web app** built with **Python**, **TensorFlow/Keras**, and **Streamlit**. It uses a trained **LSTM (Long Short-Term Memory)** model to predict the most likely next word from a user-provided text sequence.

## Project Overview

The goal of this project is to demonstrate how a recurrent neural network can learn patterns in text and suggest the next word based on the previous words. This is a common natural language processing (NLP) task and is useful for understanding sequence prediction, language modeling, and text generation.

The app loads a pre-trained model and a saved tokenizer, then uses them to convert the input text into numeric sequences, pads the sequence to the required length, and feeds it into the LSTM model. The model returns a probability distribution over the vocabulary, and the word with the highest probability is shown as the prediction.

## How It Works

1. The user enters a sentence or phrase.
2. The text is tokenized using the saved tokenizer.
3. The token sequence is padded to match the model’s expected input length.
4. The LSTM model predicts the next word.
5. The app displays the predicted word in the Streamlit interface.

## Main Components

- **Streamlit**: Used to build the interactive web interface.
- **TensorFlow/Keras**: Used to load and run the trained LSTM model.
- **Tokenizer**: Converts text into numerical tokens that the model can understand.
- **Pad Sequences**: Ensures all input sequences have the same length.
- **NumPy**: Used to identify the highest-probability prediction.

## Files Used

- `app.py` — Main Streamlit application.
- `next_word_lstm.h5` — Saved trained LSTM model.
- `tokenizer.pickle` — Saved tokenizer used during training.

## Code Explanation

### Model Loading

The application first loads the trained LSTM model and tokenizer:

```python
model = load_model('next_word_lstm.h5')
```

```python
with open('tokenizer.pickle','rb') as handle:
    tokenizer = pickle.load(handle)
```

### Next Word Prediction Function

The `predict_next_word()` function handles the prediction workflow:

- converts text into token IDs,
- trims long sequences,
- pads the input,
- runs the model prediction,
- maps the predicted class back to the corresponding word.

### Streamlit Interface

The app provides:

- a title,
- a text input box,
- a button to trigger prediction,
- an output area to display the predicted next word.

## Example

If the user enters:

> To be or not to be

The model will predict the next most likely word based on patterns it learned during training.

## Requirements

Typical dependencies for this project include:

- Python
- TensorFlow
- Streamlit
- NumPy
- Pandas
- Pickle

## How to Run

1. Install the required dependencies.
2. Make sure `next_word_lstm.h5` and `tokenizer.pickle` are present in the project directory.
3. Run the Streamlit app:

```bash
streamlit run app.py
```

## Notes

- The prediction quality depends on the training data used to build the model.
- The app predicts only one next word at a time.
- It is a learning/demo project for sequence modeling with LSTM.

## Project Summary

In short, this repository shows how to build a basic next-word prediction system using an LSTM neural network and present it through a simple Streamlit interface.
