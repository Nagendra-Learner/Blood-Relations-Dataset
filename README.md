# Blood-Relations-Dataset
This repository contains a custom-prepared Blood Relations dataset designed for training conversational models like GPT-3.5-turbo. The dataset is structured in a conversational format that focuses on family relationships and is ideal for building models capable of answering family-related queries.

# Dataset Overview:

The dataset is split into two parts:

* Training Dataset: Train_BloodRelations.jsonl (210 Samples)
* Validation Dataset: Validation_BloodRelations.jsonl (40 Samples)

Each sample in the dataset contains a structured conversation between the system, the user, and the assistant. The dataset emphasizes blood relation queries, including explanations for the answers, making it useful for training models to both answer and provide reasoning behind the answers.

# Dataset Format:
The dataset is structured as a JSON Lines (JSONL) file, where each entry follows this format:
```
{
  "messages": [
    {
      "role": "system",
      "content": "You are a helpful and knowledgeable assistant. Your task is to answer blood relations questions clearly and correctly, sometimes explaining the reasoning behind your answers when helpful."
    },
    {
      "role": "user",
      "content": "Symbols: + = brother, * = sister, - = mother. What does J*N-T+P*H imply?\nChoices:\na) N is T's mother\nb) H is P's sister\nc) P is T's brother\nd) T is P's sister"
    },
    {
      "role": "assistant",
      "content": "Answer: a) N is T's mother.\nExplanation: Breaking down the symbols: J is N's sister, N is T's mother, T is P's brother, and P is H's sister. The clearest confirmed relationship is N's maternity of T."
    }
  ]
}
```

* role: The role of the speaker in the conversation (system, user, assistant).
* system: Provides initial instructions or context to the assistant.
* user: Asks a question about blood relations.
* assistant: Responds with the answer and, if needed, provides an explanation.


# Example Entry:
Here is a sample from the dataset:
```
{
  "messages": [
    {
      "role": "system",
      "content": "You are a helpful and knowledgeable assistant. Your task is to answer blood relations questions clearly and correctly, sometimes explaining the reasoning behind your answers when helpful."
    },
    {
      "role": "user",
      "content": "Tharik describes a boy as, The youngest male sibling of my parent’s female child. How is the boy related to Tharik?\nChoices:\nA: Nephew\nB: Cousin\nC: Son\nD: Brother"
    },
    {
      "role": "assistant",
      "content": "Answer: Brother\nExplanation: Tharik’s father’s wife is his mother. Their daughter is his sister. The boy, being her younger brother, shares the same parents as Tharik, making them siblings."
    }
  ]
}
```


# Purpose:
This dataset is ideal for training or finetuning conversational models to:
Recognize and answer questions about blood relations, including the ability to reason through family dynamics.
Generate clear responses, explaining relationships between family members.
The dataset encourages both direct question-answering and reasoning, ensuring that the model not only provides an answer but also explains how it reached that conclusion.

# Usage:
To use this dataset for training a conversational model:
* Download the dataset files (Train_BloodRelations.jsonl and Validation_BloodRelations.jsonl).
* Load the JSONL files into your training pipeline.
* Preprocess the data (e.g., tokenization, padding) according to your model's requirements.
* Train your model using the training set and evaluate its performance using the validation set.


# Contributions:
Feel free to fork this repository and submit issues or pull requests for improvements, new data samples, or bug fixes.
