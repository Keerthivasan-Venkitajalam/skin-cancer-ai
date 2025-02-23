# Skin Cancer Detection

## Docker Image
[![Gen AI Exchange skin cancer AI](https://hub.docker.com/r/conero007/skin-cancer-detection)](https://hub.docker.com/repository/docker/keerrrthiv/gen-ai-exchange-hackathon-skin-cancer-detection-tool/general)

---

## Table of Contents
* [Project Summary](#summary)
* [Development Process](#process)
* [Model Creation](#model)
* [Website & Docker Image](#website)
* [References](#references)

---

## Project Summary <a name="summary"></a>
This tool predicts the probability of a mole being malignant (cancerous) using image analysis. Skin cancer is a prevalent and life-threatening disease, with millions of new cases each year. Early detection significantly improves survival rates.

### Key Statistics:
- In 2018, 18.1 million new cases and 9.6 million deaths from skin cancer were reported globally.
- Studies predict an increase in incidence rates in Europe to 40–50 cases per 100,000 people annually.
- In India, research highlights clinicopathological evaluations and the current scenario of non-melanoma skin cancers (NMSCs).
- The estimated 5-year survival rate for early-detected melanoma is 98%, but it drops to 62% when the disease spreads to lymph nodes and 18% when it metastasizes to distant organs.
- Early detection is crucial for improving survival rates.

---

## Development Process <a name="process"></a>
The core of this project is a Convolutional Neural Network (CNN) model that predicts the malignancy of a mole from an input image.

### Dataset:
We used the [HAM10000 dataset](https://www.kaggle.com/kmader/skin-cancer-mnist-ham10000), which contains dermatoscopic images of pigmented skin lesions for classification.

---

## Model Creation <a name="model"></a>
The CNN model was built from scratch with the following key components:

- **Conv2D**: Convolutional layers with consistent parameters, except for varying input and output channels.
- **MaxPool2D**: Reduces the spatial dimensions (height and width) by selecting the maximum value in a specified window.
- **BatchNormalization**: Normalizes input to stabilize training and improve convergence.
- **Dropout**: Randomly turns off a percentage of neurons during training to prevent overfitting and enhance generalization.
- **Flatten**: Converts multi-dimensional outputs into a one-dimensional tensor for classification.

---

## Website & Docker Image <a name="website"></a>
### Backend & Frontend:
- **Backend:** Built using Flask.
- **Frontend:** Developed with HTML, CSS, and Bootstrap for a responsive design.
- **File Handling:** The system validates uploaded files as images before storing them in a temporary folder (`static/`). Images are deleted after a page refresh.
- **Processing & Prediction:** Images are preprocessed before being passed to the model for classification. Results are displayed using Jinja2 templates.
- **Error Handling:** Flask's Flash messages are used for user-friendly error notifications.

### Dockerization:
- A **Dockerfile** was created to containerize the project.
- Flask was configured to run within a Docker container, dynamically fetching the allocated port.
- The final Docker image was built, tested for bugs, and pushed to [DockerHub](https://hub.docker.com/).

## References <a name="references"></a>
- [Python 3.9 Documentation](https://docs.python.org/3.9/)
- [Docker for Python](https://docs.docker.com/language/python/)
- [Flask Framework](https://flask.palletsprojects.com/en/2.0.x/)
- [TensorFlow API Docs](https://www.tensorflow.org/api_docs/python/tf/all_symbols)
- [Heroku Python Support](https://devcenter.heroku.com/categories/python-support)

---

This project demonstrates how AI can assist in early skin cancer detection through deep learning and web-based deployment, making healthcare solutions more accessible.

