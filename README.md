# WhiteLightning Model Library

Welcome to the WhiteLightning Model Library - a centralized repository for uploading, downloading, and managing trained machine learning models.

## 📋 Overview

This repository serves as a comprehensive model library where you can:
- **Upload** your trained machine learning models
- **Download** pre-trained models for your projects  
- **Share** models with team members and collaborators
- **Access** model metadata, training data, and configuration files

## 🏗️ Repository Structure

The repository is organized by model classification types:

```
whitelightning-model-library/
├── Binary/                    # Binary classification models
│   ├── hate_speech_classifier/
│   ├── sentiment_classifier/
│   └── spam_classifier/
├── Multiclass/               # Multiclass classification models
│   ├── customer_review_topic/
│   └── news_topic_clf/
└── Multiclass(Sigmoid)/      # Multilabel classification models
    ├── emotion_classifier/
    └── news_multilabel/
```

## 🤖 Available Models

### Binary Classification Models

#### 1. **Hate Speech Classifier**
- **Purpose**: Detects hate speech in text content
- **Type**: Binary classification (hate speech / not hate speech)
- **Files**: Model weights (.h5, .onnx), training data, vocabulary, scaler

#### 2. **Sentiment Classifier** 
- **Purpose**: Analyzes sentiment in text
- **Type**: Binary classification (positive / negative sentiment)
- **Files**: Model weights (.h5, .onnx), training data, vocabulary, scaler

#### 3. **Spam Classifier**
- **Purpose**: Identifies spam messages
- **Type**: Binary classification (spam / not spam)
- **Files**: Model weights (.h5, .onnx), training data, vocabulary, scaler

### Multiclass Classification Models

#### 1. **Customer Review Topic Classifier**
- **Purpose**: Categorizes customer reviews by topic
- **Type**: Multiclass classification
- **Categories**: Customer Service, Ease of Use, Price, and more
- **Files**: Model weights (.h5, .onnx), training data, vocabulary, scaler

#### 2. **News Topic Classifier**
- **Purpose**: Classifies news articles by topic
- **Type**: Multiclass classification  
- **Categories**: Business, Health, Politics, and more
- **Files**: Model weights (.h5, .onnx), training data, vocabulary, scaler

### Multilabel Classification Models (Sigmoid)

#### 1. **Emotion Classifier**
- **Purpose**: Detects multiple emotions in text simultaneously
- **Type**: Multilabel classification with sigmoid activation
- **Categories**: Fear, Happy, Love, Sadness
- **Unique Feature**: Single text can belong to multiple emotion categories
- **Files**: Model weights (.keras, .onnx), training data, vocabulary, scaler

#### 2. **News Multilabel Classifier**
- **Purpose**: Categorizes news articles into multiple topics simultaneously
- **Type**: Multilabel classification with sigmoid activation
- **Categories**: Business, Environment, Health, Politics, Sports, Technologies, Wars
- **Unique Feature**: Single article can belong to multiple news categories
- **Files**: Model weights (.keras, .onnx), training data, vocabulary, scaler

## 📁 Model Directory Structure

Each model directory contains:

```
model_name/
├── model.h5                    # Keras model file
├── model.onnx                  # ONNX model file for cross-platform deployment
├── training_data.csv           # Training dataset
├── edge_case_data.csv          # Edge case test data
├── vocab.json                  # Vocabulary mapping
├── scaler.json                 # Feature scaling parameters
├── generation_config.json      # Model generation configuration
├── *_edge_case_predictions.csv # Edge case prediction results
└── api_requests/               # API request logs and examples
    └── *.json                  # Request/response examples
```

## 🚀 How to Use

### Downloading Models

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd whitelightning-model-library
   ```

2. **Navigate to desired model**:
   ```bash
   cd Binary/sentiment_classifier/  # Example
   ```

3. **Load the model in your code**:
   ```python
   # For Keras models
   from tensorflow.keras.models import load_model
   model = load_model('model.h5')
   
   # For ONNX models
   import onnxruntime as ort
   session = ort.InferenceSession('model.onnx')
   ```

### Uploading New Models

1. **Create a new directory** under the appropriate classification type:
   ```bash
   mkdir Binary/your_model_name/
   # or
   mkdir Multiclass/your_model_name/
   # or
   mkdir "Multiclass(Sigmoid)/your_model_name/"
   ```

2. **Add required files**:
   - `model.h5` - Keras model
   - `model.onnx` - ONNX model (optional but recommended)
   - `training_data.csv` - Training dataset
   - `vocab.json` - Vocabulary file
   - `scaler.json` - Scaler parameters
   - `generation_config.json` - Model configuration
   - `edge_case_data.csv` - Test cases (optional)

3. **Commit and push**:
   ```bash
   git add .
   git commit -m "Add new model: your_model_name"
   git push origin main
   ```

## 📊 Model Formats

- **Keras (.h5)**: Native TensorFlow/Keras format
- **ONNX (.onnx)**: Cross-platform format for deployment
- **JSON files**: Configuration and vocabulary data
- **CSV files**: Training and test datasets

## 🔧 Requirements

- Python 3.7+
- TensorFlow/Keras (for .h5 models)
- ONNX Runtime (for .onnx models)
- pandas, numpy (for data handling)

## 📝 Contributing

1. Fork the repository
2. Create a feature branch
3. Add your model following the directory structure
4. Submit a pull request with model description

## ⚡  Main Repo

[WhiteLightning](https://github.com/Inoxoft/whitelightning) distills massive, state-of-the-art language models into lightweight, hyper-efficient text classifiers. It's a command-line tool that lets you create specialized models that run anywhere—from the cloud to the edge—using the universal ONNX format for maximum compatibility.

## 🌐 Documentation & Website

Need comprehensive guides and documentation? Check out our [WhiteLightning Site](https://github.com/whitelightning-ai/whitelightning-site) - this repository hosts the official website for WhiteLightning at https://whitelightning.ai, a cutting-edge LLM distillation tool with detailed documentation, tutorials, and implementation guides.

## 🧪 Testing & Validation

Want to test your ONNX models across multiple programming languages? Check out our [WhiteLightning Test Framework](https://github.com/Inoxoft/whitelightning) - a comprehensive cross-language testing suite that validates your models in:

* **8 Programming Languages**: Python, Java, C++, C, Node.js, Rust, Dart, and Swift
* **Performance Benchmarking**: Detailed timing, memory usage, and throughput analysis
* **Automated Testing**: GitHub Actions workflows for continuous validation
* **Real-world Scenarios**: Test with custom inputs and edge cases

Perfect for ensuring your WhiteLightning models work consistently across all target platforms and deployment environments.

## 📞 Support

For questions or issue regarding the model library, please:
- Open an issues in this repository
- Contact the WhiteLightning team

## License

This project is licensed under the [MIT License](./LICENSE).

**Happy modeling! 🚀** 