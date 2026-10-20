# House Price Prediction (Django + ML)

A Django web app that predicts house prices with a pre-trained scikit-learn model (loaded with joblib) from eight property features entered in a web form.

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?logo=django&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)

## Overview

Originally developed inside a Django projects collection, this project now lives in its own repository. It shows the classic pattern for serving an ML model on the web: train offline, serialize with joblib, load once in the view, and predict from form input.

## How It Works

1. The form collects: bedrooms, space, rooms, lot size, tax, bathrooms, garage and condition
2. `prediction/views.py` loads the trained model (`prediction/model/house.pkl`) with joblib
3. The model returns a predicted price, rendered back on the same page

## Tech Stack

Python · Django · scikit-learn · joblib · NumPy · SQLite

## Project Structure

```
├── house_price/    # Project settings, URLs, WSGI/ASGI
├── prediction/     # App: views, URLs, model/ (trained .pkl — see Notes)
└── manage.py
```

## Getting Started

```bash
git clone https://github.com/datascientist970/house-price-prediction-django.git
cd house-price-prediction-django
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

## Notes

- The trained model file (`prediction/model/house.pkl`, binary) is not included in this repository copy — place a joblib-saved model trained on the eight features above at that path before running predictions.
- The development database (`db.sqlite3`) is intentionally not tracked — run `migrate` for a fresh database.
- Split out of the `Web-Development-Django-` collection into its own repository.

## Author

**Muhammad Dawood** — AI & Data Science Engineer | Full-Stack Developer
GitHub: https://github.com/datascientist970 · LinkedIn: https://www.linkedin.com/in/dawood406/
Mardan, Khyber Pakhtunkhwa, Pakistan
