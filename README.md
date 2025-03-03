---
license: mit
language:
- en
metrics:
- accuracy 97%
base_model:
- distilbert/distilbert-base-uncased
pipeline_tag: text-classification
---
# Last Name Classification Model
[![Support](https://img.shields.io/badge/Support-Us-brightgreen)](https://nowpayments.io/donation/Vishodi)

A Transformer-based classifier that checks if a provided last name is likely to be **real** (LABEL_1) or **fake** (LABEL_0). This can be helpful in validating contact form submissions, preventing bot entries, or for general name classification tasks.

## Table of Contents
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Support Me](#support-me)
- [License](#license)

## Project Structure
```plaintext
Last_Name_Prediction/
├── .gitattributes
├── README.md
├── config.json
├── model.safetensors
├── requirements.txt
├── special_tokens_map.json
├── tokenizer.json
├── tokenizer_config.json
└── vocab.txt
```

## Installation
1. **Clone the Repository:**
```bash
git clone https://github.com/Vishodi/First-Name-Classification.git
```

2. **Set Up the Environment:**
   Install the required packages using pip:
```bash
pip install -r requirements.txt
```

## Usage
```python
from transformers import pipeline

# Replace with your model repository
model_dir = "vishodi/First-Name-Classification"

# Load the model pipeline with authentication
classifier = pipeline(
    "text-classification",
    model=model_dir,
    tokenizer=model_dir,
)

# Test the model
test_names = ["Mark", "vcbcvb", "uhyhu", "elon"]
for name in test_names:
    result = classifier(name)
    label = result[0]['label']
    score = result[0]['score']
    print(f"Name: {name} => Prediction: {label}, Score: {score:.4f}")
```

**Output:**
```
Name: Mark => Prediction: LABEL_1, Score: 0.9994
Name: vcbcvb => Prediction: LABEL_0, Score: 0.9985
Name: uhyhu => Prediction: LABEL_0, Score: 0.9982
Name: elon => Prediction: LABEL_1, Score: 0.9987
```

## Support Us
[![Support Us](https://img.shields.io/badge/Support-Us-brightgreen)](https://nowpayments.io/donation/Vishodi)

## License
This project is licensed under the MIT License.
