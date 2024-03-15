# Medical Diagnosis Assistant: Integrating Neural Networks and Language Models for Automated Analysis of X-Rays

## About

In the radiology world, radiologists must analyze an ever-increasing volume of X-ray images on a daily basis due to the exponential rise of medical imaging. This demanding pace not only poses challenges for accurate diagnosis but also strains the efficiency and effectiveness of healthcare delivery. Recognizing the pressing need for transformative solutions in this domain, we aim to automate  this process by creating a way to use a Large Language Model (LLM) to analyze X-ray image input and generate a text radiology report, similar to ChatGPT. By applying this technology to the field of radiology, we seek to augment diagnostic accuracy while optimizing the operational workflow of this area of healthcare for the benefit of both radiologists and patients.

## Methods

### Data

We analyzed approximately 23,000 X-Ray images from patients at UC San Diego Health collected over the years. We also had patient history data, diagnosis from the X-Ray images, and other demographic clinical data that we used to analyze the X-Ray image diagnoses. 

#### LLaVA (Large Language and Vision Assistant): 
A large multi-modal model that combines a vision encoder and Vicuna LLM that achieves impressive chat capabilities.

<p align="center">
    <img src="LLaVA_architecture.png" alt="LLaVA Architecture" width="500">
</p>

#### Baseline Model: 
Building off of the LLaVA framework, we fine-tuned the model on a dataset of 23,000 X-ray images with findings and impressions only.

#### Areas of Improvements:
To improve model accuracy, we integrate more context data into training such as clinical history and gender, as well as explore evaluation metrics and benchmarking. By doing so, facilitating a more informed assessment of condition severity, thereby enhancing the overall accuracy of the model's outputs.


## Evaluation Metrics

### NLP Techniques and Similarity Scoring
We applied traditional NLP techniques and compared both models with the ground truth (radiologist reports) using similarity scores. Specifically, we vectorized the text reports using Term Frequency - Inverse Document Frequency (TF-IDF) and performed cosine similarity to produce a similarity score that quantifies model performance in terms of sentence structure development and general similarity to real radiology reports. 

### OpenAI GPT-3.5 Turbo:
To assess the accuracy of model-generated reports across various disease entities, we employed the GPT-3.5 Turbo model developed by OpenAI. The use of LLM facilitated the extraction of the presence and severity of each disease entity from both the original reports and generated reports. Then, we quantified the model's accuracy by comparing the severity classes identified in the generated reports against those in the original reports. This approach may offer a more effective approach to evaluating diagnostic accuracy and severity assessment of disease entities, due to its enhanced ability to interpret complex sentence structures and contexts, which could potentially improve upon the limitations of traditional NLP methods.


## Results

#### NLP Similarity Scores Evaluation:
Baseline model performance - TF-IDF encoding and cosine similarity:

![Baseline Model Performance Similarity Scores](dsc180bsimilarityplot.png){ width=200px }

Final model with clinical context performance - TF-IDF encoding and cosine similarity

![Final Model Performance Similarity Scores](dsc180bcontextsimscores.PNG){ width=200px }

#### LLM-assisted Evaluation: 
Baseline model performance by disease entity:

- Pneumothorax: 0.966
- Pleural Effusion: 0.708
- Cardiomegaly: 0.683
- Rib Fracture: 0.666
- Edema: 0.641
- Pneumonia: 0.424

![Baseline Model Performance by Disease Entity](model1_results.png)

## Example Inference

<p align="center">
    <img src="xray_example.jpg" alt="Example X-ray" width="500">
</p>

**Prompt**: Given this radiology report. Could you provide a detailed interpretation of the findings in this chest X-ray?

**Radiology Report**: Enlarged cardiac silhouette, as before. enlarged central pulmonary arteries, consistent with pulmonary hypertension. left midlung and bibasal streaky densities consistent with subsegmental atelectasis or scarring.

**LLaVA**: Findings of pulmonary hypertension with pulmonary edema.


## Conculsion

By using LLM-assisted evaluation, the process of extracting  sentiment from complex sentence constructions in the reports is automated, which offers a nuanced assessment of the diagnostic accuracy concerning specific diseases, but may present a lack of consistency. This form of evaluation necessitates further testing to ensure thoroughness and accuracy.
On the other hand, NLP method of evaluation provides a way of comparing the overall similarity of the LLaVA predicted responses to the ground truth of radiologist reports, but detailed semantics may not be extracted.



## The Team
Sally Yu
Eudora Fong
Aishani Mohapatra

