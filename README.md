# Medical Diagnosis Assistant: Integrating Neural Networks and Language Models for Automated Analysis of X-Rays

## About

In the radiology world, radiologists must analyze an ever-increasing volume of X-ray images on a daily basis due to the exponential rise of medical imaging. This demanding pace not only poses challenges for accurate diagnosis but also strains the efficiency and effectiveness of healthcare delivery. Recognizing the pressing need for transformative solutions in this domain, we aim to automate  this process by creating a way to use a Large Language Model (LLM) to analyze X-ray image input and generate a text radiology report, similar to ChatGPT. By applying this technology to the field of radiology, we seek to augment diagnostic accuracy while optimizing the operational workflow of this area of healthcare for the benefit of both radiologists and patients.

## Methodology

### Data

We analyzed approximately 23,000 X-Ray images from patients at UC San Diego Health collected over the years. We also had patient history data, diagnosis from the X-Ray images, and other demographic clinical data that we used to analyze the X-Ray image diagnoses. 

*Insert X-Ray Image*

### LLaVA (Large Language and Vision Assistant): 
A large multi-modal model that combines a vision encoder and Vicuna LLM that achieves impressive chat capabilities.

*Insert Image of how LLaVA works *

### Baseline Model: 
Building off of the LLaVA framework, we fine-tuned the model on a dataset of 23,000 X-ray images with findings and impressions only.

### Areas of Improvements:
To improve model accuracy, we intend to integrate more context data into training such as clinical history and gender. By doing so, facilitating a more informed assessment of condition severity, thereby enhancing the overall accuracy of the model's outputs.



## Results

### LLM-assisted Evaluation: 
Baseline model performance by disease entity:

Pneumothorax: 0.966
Pleural Effusion: 0.708
Cardiomegaly: 0.683
Rib Fracture: 0.666
Edema: 0.641
Pneumonia: 0.424

*Insert Image of Accuracy Bar Graph*


### NLP Similarity Scores Evaluation:
Baseline model performance using TF-IDF encoding and cosine similarity:

*Insert Cosine Similarity Graph*



## Conculsion



## The Team


