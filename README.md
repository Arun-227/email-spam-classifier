# Email Spam Classifier

A Flask web app that classifies a message as spam or ham using a TF-IDF and
Multinomial Naive Bayes pipeline.

## Project structure

```text
backend/
  app.py
  predict_email.py
  spam_model.joblib
  train_model.py
  requirements.txt
  static/
  templates/
dataset/
```

The trained model is included, so the web app can run without downloading the
training dataset. `train_model.py` downloads the SMS Spam Collection dataset
when retraining; the dataset itself is not stored in this repository.

## Run locally

Use Python 3.10 or newer. From the `backend` directory, install the dependencies
and start the Flask app:

```powershell
cd backend
python -m pip install -r requirements.txt
python app.py
```

Open the local address printed by Flask in your browser. The development server
is intended for local use, not production deployment.

## Retrain the model

From the `backend` directory, run:

```powershell
python train_model.py
```

The script downloads the dataset, evaluates the model, and writes the updated
pipeline to `backend/spam_model.joblib`.
