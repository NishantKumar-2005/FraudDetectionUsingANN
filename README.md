Fraud Detection API

This API is designed to detect whether a financial transaction is fraudulent or not. It uses a hybrid model combining an Artificial Neural Network (ANN) and a BERT model for Natural Language Processing (NLP) to analyze transaction messages and other key features.

Features

Detects if a transaction is fraudulent based on structured data and transaction messages.

Utilizes BERT for message encoding and ANN for classification.

REST API endpoint for easy integration.

Requirements

Python 3.11+

Flask

PyTorch

Transformers

scikit-learn

pandas

Installation

Clone the repository:

git clone https://github.com/your-repo/fraud-detection-api.git
cd fraud-detection-api

Create a virtual environment (optional but recommended):

python -m venv venv
source venv/bin/activate  # For Linux/macOS
.\venv\Scripts\activate   # For Windows

Install dependencies:

pip install -r requirements.txt

Ensure the trained model file fraud_detection_model.pth is in the root directory.

Usage

Run the API

python app.py

API Endpoint

POST /predict

Request Body:

{
    "message": "Transaction of $1000 from account X to account Y."
}

Response:

{
    "is_fraudulent": "Yes" or "No"
}

Model Details

Neural Network (ANN)

Input: Transaction features (encoded categorical and numerical data)

Hidden Layers: Configurable (default 3 layers, 64 neurons each)

Activation: ReLU

Dropout: 0.5

Output: Binary classification (Fraud/Not Fraud)

BERT Model

Pre-trained bert-base-uncased model from Hugging Face

Message embeddings are extracted using mean pooling

Customization

You can customize the neural network architecture by adjusting the following parameters in the MyNN class:

input_dim: Number of input features

output_dim: Number of output classes (2 for binary classification)

no_of_HiddenLayer: Number of hidden layers

no_of_neurons: Number of neurons per hidden layer

no_of_Dropout: Dropout rate

License

MIT License

Acknowledgements

Hugging Face Transformers

PyTorch

Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Author

Nishant Kumar

