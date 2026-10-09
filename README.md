# WhisperScale: Function-Preserving Scaling of Whisper for Multilingual Indic Speech Recognition

## Project Objective

WhisperScale explores function-preserving scaling of pretrained Whisper models for multilingual speech recognition. The project focuses on converting audio recordings into text in the spoken language using a scaled version of OpenAI's Whisper-small and the FLEURS multilingual speech dataset.

The approach widens pretrained feed-forward networks while retaining the original weights and initializing the additional parameters to preserve the model's original functionality at initialization.

## Key Features

- **Function-preserving scaling:** Expand pretrained feed-forward networks while retaining the original model's functionality.
- **Multilingual speech recognition:** Evaluate performance across 8 Indic languages.
- **Pretrained architecture:** Build on OpenAI's Whisper-small.
- **Transcription evaluation:** Measure performance using Word Error Rate (WER) and Character Error Rate (CER).

## Model Architecture

| Component | Details |
|---|---|
| Base model | Whisper-small |
| Scaled model size | Approximately 440M parameters |
| Encoder feed-forward width | 6,144 |
| Decoder feed-forward width | 21,504 |
| Scaling strategy | Function-preserving feed-forward network widening |
| Task | Audio-to-text transcription |

## Dataset

The project uses the [**FLEURS dataset**](https://huggingface.co/datasets/google/fleurs), a multilingual speech recognition benchmark.

Experiments cover **8 Indic languages**:

| Language | FLEURS code |
|---|---|
| Bengali | `bn_in` |
| Gujarati | `gu_in` |
| Hindi | `hi_in` |
| Kannada | `kn_in` |
| Malayalam | `ml_in` |
| Marathi | `mr_in` |
| Tamil | `ta_in` |
| Telugu | `te_in` |

The reported experiment uses **48,000 training instances** across the selected languages.

## Results

| Evaluation Metric | Result |
|---|---:|
| Word Error Rate (WER) | **36.66%** |
| Character Error Rate (CER) | **9.76%** |

- **WER:** Measures transcription errors at the word level.
- **CER:** Measures transcription errors at the character level.

Lower values indicate better transcription accuracy. These are the reported results of the experiment and should be interpreted in the context of its training and evaluation setup.

## Technologies Used

- Python
- PyTorch
- Hugging Face Transformers
- Hugging Face Datasets
- Whisper-small
- FLEURS