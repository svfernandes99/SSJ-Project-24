# -Mental-Health-Condition-Monitoring-from-Social-Media

## Project Title: Mental Health Condition Monitoring from Social Media.
![image](https://github.com/user-attachments/assets/1763c8f1-23dc-4c0a-9b8d-7f6ea6f3a3b4)

<img width="635" alt="image" src="https://github.com/user-attachments/assets/e590115b-0d90-4f18-ad78-1bc89af1aa97">


## Introduction

In recent years, there has been growing recognition of the importance of mental health and well-being. However, identifying and addressing mental health conditions in a timely manner remains a significant challenge. Traditional methods of monitoring mental health, such as clinical assessments and surveys, often suffer from limitations such as high cost, stigma, and delays in data collection and analysis.Mental health conditions, including depression, anxiety, and suicidal ideation, affect millions of individuals worldwide. Social media platforms have emerged as a valuable source of data for monitoring and understanding mental health trends and behaviours.
This project aims to leverage natural language processing (NLP) techniques to analyze social media posts, particularly tweets from Twitter, to detect signs of mental health conditions and identify individuals at risk of suicidal ideation. By harnessing the power of social media data, we seek to provide early interventions and support for those in distress.

## Objectives

1) Machine Learning Models for Linguistic Markers: Develop machine learning models capable of detecting linguistic markers and patterns indicative of mental health conditions, such as depression and suicidal ideation, within social media posts.

2) Actionable Alerts for Timely Interventions: Provide actionable alerts generated by the system to mental health professionals, crisis intervention teams, and social media platform moderators. These alerts facilitate timely interventions and support for individuals identified as being at risk, thereby potentially preventing self-harm or suicide attempts.
These objectives outline a comprehensive approach aimed at leveraging machine learning and real-time monitoring technologies to address mental health challenges on social media platforms effectively.

## Dataset:
<img width="727" alt="image" src="https://github.com/user-attachments/assets/19700136-7cde-49aa-8a07-291abee4118d">


### Dataset Details

The dataset utilized in this analysis originates from Kaggle and comprises posts from the "SuicideWatch" and "depression" subreddits on Reddit, acquired through the Pushshift API.
Specifically, posts from "SuicideWatch" were collected from December 16, 2008 (the subreddit's inception) to January 2, 2021.

Posts from the "depression" subreddit were gathered from January 1, 2009, to January 2, 2021.

Categorized labeling assigns posts from "SuicideWatch" as suicide-related, while those from the "depression" subreddit are marked as pertaining to depression.

Additionally, non-suicidal posts are drawn from the "teenagers" subreddit.

Initially, the dataset featured labels solely for suicide and non-suicide posts.

Subsequent iterations, such as version V13, expanded the labeling scheme to encompass depression and normal conversations among teenagers.

Supplementary documentation, in the form of a notebook, illustrates the methodology for obtaining Reddit posts via the PushShift API.

## Technologies Used

## Data Preprocessing and Augmentation


## AI Models Used
Model Description
Summary:Long short-term memory (LSTM) is a type of recurrent neural network (RNN)
aimed at dealing with the vanishing gradient problem present in traditional RNNs. Its relative
insensitivity to gap length is its advantage over other RNNs, hidden Markov models and other
sequence learning methods. It aims to provide a short-term memory for RNN that can last
thousands of timesteps, thus "long short-term memory". It is applicable to classification,
processing and predicting data based on time series, such as in handwriting, speech recognition,
machine translation, speech activity detection,robot control video games,and healthcare.
CNN is a deep learning model commonly used for image recognition tasks, but it can also be
applied to sequential data such as text through the use of 1D convolutions.
Usage in Project: LSTM and CNN was adapted for text classification to capture local patterns
and features within social media posts. It learned to detect specific linguistic patterns associated
with suicidal ideation, aiding in the detection process.
These models, along with K-Fold Cross-Validation, collectively formed the core components of
the project's machine learning pipeline. They were instrumental in developing a comprehensive
system for detecting linguistic markers and patterns associated with mental health conditions in
social media posts, ultimately contributing to the goal of early intervention and support for
at-risk individuals.
The model architecture is constructed using the Keras Sequential API, comprising several layers
designed for text classification tasks:
6
The project incorporates deep learning with following Layers
Embedding Layer:
Input Dimension: 10,000 (Vocabulary Size)
Output Dimension: 16
Input Length: 200 (Maximum Sequence Length)
The Embedding layer converts input text data into dense vectors of fixed size. It learns a dense
representation for each word in the vocabulary, with the output dimensionality set to 16.
The Embedding layer serves as the initial step in processing text data within the model
architecture. With a vocabulary size of 10,000 and an input length of 200, this layer transforms
input text sequences into dense vectors of fixed size, each representing a word in the vocabulary.
By setting the output dimensionality to 16, the Embedding layer learns a compact and
meaningful representation for each word, facilitating the model's ability to capture semantic
similarities and relationships between words. These dense embeddings encode contextual
information and semantic meaning, enabling the subsequent layers to effectively process and
understand the textual input.
Convolutional 1D Layer:
Filters: 32 ; Kernel Size: 5 ; Activation Function: ReLU
The Conv1D layer applies 32 filters of size 5 to the embedded sequences, extracting local
features from the text data. The ReLU activation function introduces non-linearity to the model.
The Embedding layer serves as the initial step in processing text data within the model
architecture. With a vocabulary size of 10,000 and an input length of 200, this layer transforms
input text sequences into dense vectors of fixed size, each representing a word in the vocabulary.
By setting the output dimensionality to 16, the Embedding layer learns a compact and
meaningful representation for each word, facilitating the model's ability to capture semantic
7
similarities and relationships between words. These dense embeddings encode contextual
information and semantic meaning, enabling the subsequent layers to effectively process and
understand the textual input.
MaxPooling 1D Layer:
Pool Size: 4
The MaxPooling1D layer reduces the dimensionality of the feature maps generated by the
convolutional layer, retaining the most significant features while discarding less relevant
information.
MaxPooling1D operation effectively retains the most salient features while discarding less
informative details. This process enhances the model's ability to focus on the most discriminative
aspects of the input data, enabling it to extract and emphasize key patterns and characteristics
essential for accurate classification or prediction tasks. Additionally, the MaxPooling1D layer
contributes to the overall efficiency of the model by reducing the computational burden and
parameter count, thereby improving training speed and memory efficiency. Overall, the
MaxPooling1D layer plays a vital role in enhancing the model's robustness, interpretability, and
computational efficiency, making it an indispensable component in various neural network
architectures designed for one-dimensional data processing tasks like text classification and
sentiment analysis.
Bidirectional LSTM Layer:
Units: 32
Activation Function: tanh (Hyperbolic Tangent) , Recurrent Activation Function: sigmoid
(Sigmoid)
The Bidirectional LSTM (Long Short-Term Memory) layer is a cornerstone of modern neural
8
network architectures, particularly in the realm of natural language processing (NLP). Its
integration within the model architecture harnesses the inherent strengths of LSTM units in
capturing intricate patterns and long-range dependencies present in sequential data, such as text
sequences. Configured with 32 units and a dropout rate of 0.4, this layer operates bidirectionally,
enabling the model to glean insights from both past and future contexts simultaneously. This
bidirectional processing capability is instrumental in capturing the temporal dynamics and
contextuality inherent in language, allowing the model to develop a comprehensive
understanding of the input sequences.
The activation function used within the Bidirectional LSTM layer is hyperbolic tangent (tanh),
which introduces non-linearity to the transformations applied to the input data. This non-linear
activation function enables the model to capture complex relationships and representations
within the text data, enhancing its ability to discern subtle nuances and patterns. Additionally, the
recurrent dropout mechanism, set to 0, serves as a regularization technique to mitigate the risk of
overfitting. By randomly dropping connections within the LSTM units during training, recurrent
dropout promotes generalization and improves the model's performance on unseen data, thereby
enhancing its robustness and reliability.
In combination, these layers form a cohesive and powerful framework for processing and
understanding textual input. The Bidirectional LSTM layer, with its ability to capture long-range
dependencies and contextual information, serves as the backbone of the model architecture,
enabling it to learn meaningful representations and make accurate predictions in various NLP
tasks. From sentiment analysis to language translation, the Bidirectional LSTM layer empowers
the model to navigate the intricacies of language, providing invaluable insights and capabilities
in the realm of natural language understanding and processing.
The Bidirectional LSTM (BiLSTM) layer consists of two LSTM layers, processing input
sequences in both forward and backward directions. This allows the model to capture long-range
dependencies and contextual information effectively. Dropout regularization with a rate of 0.4 is
applied to mitigate overfitting.
9
Dense Layer
Units: 1 Activation Function: Sigmoid
The Dense layer with a single unit and sigmoid activation function outputs the probability of the
input text belonging to the positive class (suicidal) or negative class (non-suicidal).
The model architecture combines convolutional and recurrent neural network components,
leveraging both local and sequential information in the input text data for improved classification
performance.
This model architecture is designed for text classification tasks, specifically for identifying
suicidal ideation in social media posts. It utilizes a combination of convolutional and recurrent
layers to capture both local and sequential patterns in the text data.
## Model Performances

## Overall Accuracy of all Models Comparison Plot

## Results
<img width="634" alt="image" src="https://github.com/user-attachments/assets/95495147-9c69-4348-b5ec-4507476e46ae">


## Future Scope and Limitations
Future Scope:
Multi-platform Integration: Extend analysis to multiple social media platforms.
Multimodal Analysis: Incorporate diverse data types like images and audio.
Real-time Intervention: Implement immediate support mechanisms.
Longitudinal Analysis: Track changes in mental health states over time.
User Engagement Monitoring: Identify individuals at risk of social isolation.

Limitations:
Data Bias: Risk of biased training data.
Privacy Concerns: Need for stringent data protection measures.
Algorithmic Accuracy: Models may produce false results.
Generalization Challenges: Performance variation across demographics.
Ethical Considerations: Stigmatization and consent concerns must be addressed.


## Conclusion

In conclusion, our project represents a significant stride towards harnessing the power of machine learning and deep learning techniques for early detection and intervention in mental health crises through analysis of social media content. By leveraging models such as Convolutional Neural Networks (CNN) and employing K-fold cross validation, we have developed a robust system capable of identifying linguistic markers and patterns associated with mental health conditions, including depression and suicidal ideation.
Through the integration of these models into a scalable, real-time monitoring system for social media platforms like Twitter, we have paved the way for proactive identification of individuals at risk of self-harm or suicide. Our project not only offers actionable alerts to mental health professionals, crisis intervention teams, and platform moderators but also underscores the ethical imperative of responsible AI-driven interventions in mental health. As we continue to refine and expand upon our methodologies and technologies, we remain steadfast in our commitment to leveraging cutting-edge advancements in machine learning for the betterment of society. Together, we can strive towards a future where early detection, timely intervention, and compassionate support are the cornerstones of mental health care in the digital age.


## REFERENCES
Aldhyani THH, Alsubari SN, Alshebami AS, Alkahtani H, Ahmed ZAT. Detecting and Analyzing Suicidal Ideation on Social Media Using Deep Learning and Machine Learning Models. Int J Environ Res Public Health. 2022 Oct 3;19(19):12635. doi: 10.3390/ijerph191912635. PMID: 36231935; PMCID: PMC9565132.
https://www.kaggle.com/datasets/nikhileswarkomati/suicide-watch


## Authors/Contributors


- [Resham Hansdah](https://github.com/Resham0007)
- [Sonali Kishan](https://github.com/sonalikishan)
- [Subham Beura](https://github.com/Subham-Beura/Subham-Beura)
