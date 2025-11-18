# Phishing Emails Detection

This project aims to detect phishing emails using federated learning for OS Android. The application processes emails for feature extraction and uses those features in a machine learning process as a dynamicly created datasets for phishing email classification. It also allows training and retraining of the model on new data, evaluating models, and includes a federated server for model`s weight management.

![fl](https://github.com/martinszuc/phishing-emails-detection/assets/100486753/7965ae5e-9ff2-4d95-a1f4-9390d5733c72)


## Usage

### Email Processing

The app can import emails from various sources and process them for feature extraction.

#### Import Emails

- **Gmail Import**: Users can use their Google account to import emails directly from Gmail.
<img src="https://github.com/martinszuc/phishing-emails-detection/assets/100486753/a835b65f-7025-4869-b095-ab002a7e3677" alt="Gmail Import" height="600">

- **EML Import**: Users can import individual `.eml` files.
<img src="https://github.com/martinszuc/phishing-emails-detection/assets/100486753/29489c64-02ca-4279-ae59-07021992cda1" alt="EML Import" height="600">

- **MBOX Import**: Users can import `.mbox` files containing multiple emails.

When importing, users are asked to label the emails as `phishing` or `safe`.

#### Email Packaging

- **Email Packaging**: Users can combine multiple emails into packages for processing.
<img src="https://github.com/martinszuc/phishing-emails-detection/assets/100486753/48a18d59-4438-4699-9ffc-7e2f25dd291c" alt="Email Packaging" height="600">

### Machine Learning

The app provides several features for machine learning, including feature extraction, training, and retraining.

#### Feature Extraction

- **Feature Extraction**: Users can extract features from emails using Python integration.
<img src="https://github.com/martinszuc/phishing-emails-detection/assets/100486753/b2e7e604-f226-450d-9d92-cb0418f086a2" alt="Feature Extraction" height="600">

#### Training

- **Training**: Users can train the model on the extracted features.
<img src="https://github.com/martinszuc/phishing-emails-detection/assets/100486753/4e182d17-d32d-4b26-93bb-267ec4c5cbac" alt="Training" height="600">

#### Retraining

- **Retraining**: Users can retrain the model with new data.
 <img src="https://github.com/martinszuc/phishing-emails-detection/assets/100486753/368f8a85-4a48-4bcd-91e3-ca00dc5c19cc" alt="Retraining" height="600">

#### Model Evaluation

- **Model Evaluation**: Users can evaluate the performance of the trained model.
<img src="https://github.com/martinszuc/phishing-emails-detection/assets/100486753/ac0560df-922f-4ee4-bc8f-f7e50f0cce14" alt="Model Evaluation" height="600">

### Phishing Detection

- **Phishing Detection**: Users can use the selected model to classify a single email as phishing or safe using logistic regression.
<img src="https://github.com/martinszuc/phishing-emails-detection/assets/100486753/8a2c7223-3099-47f4-8f63-b5680b044a8b" alt="Phishing Detection" height="600">

### Federated Server Usage

The federated server handles weight management for federated learning.

#### Endpoints

- **Upload Weights**: Users can upload the local model weights.
<img src="https://github.com/martinszuc/phishing-emails-detection/assets/100486753/2178f6cf-712e-42d1-969c-0fbf4ee116e5" alt="Weights Upload" height="600">

- **Download Global Weights**: Users can download the globally averaged weights.

- **Check Server Status**: Users can ping the server to check its status.
<img src="https://github.com/martinszuc/phishing-emails-detection/assets/100486753/3a83af5c-910c-4bc8-ad5d-675a95baf7fe" alt="Server Status" height="600">

## Features
- **Google Login**: Users can log in using their Google account.
- **Logout**: Users can log out from their account.
- **Integration with Gmail API**: Seamless integration with Gmail API for importing emails.
- **Email Import**: Users can import emails from Gmail, `.eml`, and `.mbox` files.
- **Email Labeling**: Users can label imported emails as `phishing` or `safe`.
- **Email Packaging**: Combine multiple emails into packages for processing.
- **Feature Extraction**: Extract features from emails using integrated Python scripts.
- **Machine Learning**:
  - **Training**: Train the model on extracted features.
  - **Retraining**: Retrain the model with new data.
  - **Model Evaluation**: Evaluate the performance of trained models.
- **Phishing Detection**: Classify individual emails as phishing or safe using logistic regression.
- **Federated Learning**:
  - **Upload Weights**: Upload local model weights to the federated server.
  - **Download Weights**: Download globally averaged weights from the server.
  - **Server Status**: Check the operational status of the federated server.
  - **Set Federated Server IP**: Dynamically set the IP address of the federated server.

## Architecture

The project is structured to separate concerns and ensure modularity. Below is an overview of the main directories and their purposes:

### Key Components:

- **Data**: Contains data-related classes, repositories, and entities for handling email data.
    - **Local**: Local data sources and caches.
    - **Remote**: Manages remote data sources, such as API calls.
    - **Repositories**: Interfaces for data access and management.
    - **Auth**: Handles user authentication.
    - **DB**: Database configurations and access.
      - **Entity**: Entity classes representing different data models such as `EmailFull`, `EmailMinimal`, `EmailPackageMetadata`, etc.

- **Python**: Contains Python scripts and modules for machine learning and data processing.
  - **DataProcessing**: Scripts for processing email data.
  - **EvaluateModel**: Scripts for evaluating models.
  - **Prediction**: Scripts for making predictions.
  - **Retraining**: Scripts for retraining models.
  - **Training**: Scripts for training models.
  - **WeightManager**: Manages model weights.
  - **PythonSingleton**: Singleton class for Python which starts and holds Python interpreter.

- **DI**: Dependency injection modules.
  - **AppModule**: Provides application-wide dependencies.
  - **DatabaseModule**: Provides database-related dependencies.
  - **NetworkModule**: Provides network-related dependencies.

- **UI**: User interface components.
  - **Base**: Base classes for UI components.
  - **component**: Specific UI components for authentication, email detection, machine learning, and settings.
  - **App**: Main application class.
  - **MainActivity**: Main activity of the application.
  - **Utils**: Utility classes and functions.
 

### Acknowledgments and References

This project builds upon and extends the work found at [MachineLearningPhishing](https://github.com/diegoocampoh/MachineLearningPhishing) by Diego Ocampo.

### Data Sources

The data used for training the phishing detection model were sourced from two main repositories, which provided a rich dataset of phishing emails:

- [Phishing Pot Dataset](https://github.com/rf-peixoto/phishing_pot) by rf-peixoto (converted .eml to mbox using scripts in this repo)
- [Phishing Dataset](https://monkey.org/~jose/phishing/) by jose at monkey.org (downloaded mbox files)

<img width="277" height="489" alt="Screenshot 2025-11-18 214411" src="https://github.com/user-attachments/assets/b741f737-cfe0-429f-906b-cf9970bd66cc" />

<img width="274" height="487" alt="Screenshot 2025-11-18 214423" src="https://github.com/user-attachments/assets/a6719259-c92b-433d-8227-d8ddf1a0b01a" />

<img width="271" height="489" alt="Screenshot 2025-11-18 214430" src="https://github.com/user-attachments/assets/13dfac21-c8fa-4385-96a5-3dc9ebf1256c" />

<img width="410" height="733" alt="Screenshot 2025-11-18 210830" src="https://github.com/user-attachments/assets/809a1068-a82a-42b9-b45d-ec18d949cf63" />



