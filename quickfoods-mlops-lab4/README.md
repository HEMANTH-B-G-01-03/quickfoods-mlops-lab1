# QuickFoods MLOps Lab 4 - Docker Model Packaging

## Objective

Package a trained machine learning model into a Docker container and run predictions consistently across environments.

## Project Structure

quickfoods-mlops-lab4/

├── data/
│   └── delivery_times.csv

├── models/
│   └── delivery_time_model.pkl

├── src/
│   ├── **init**.py
│   └── predict_cli.py

├── Dockerfile

├── requirements.txt

├── README.md

└── .gitignore

## Features

* Loads trained delivery time prediction model
* Accepts input through command-line arguments
* Predicts delivery time in minutes
* Returns prediction in JSON format
* Runs inside Docker container

## Local Execution

```bash
python src/predict_cli.py \
--distance_km 4.2 \
--items_count 3 \
--is_peak_hour 1 \
--traffic_level 2
```

## Docker Build

```bash
docker build -t quickfoods-delivery-model:0.1 .
```

## Docker Run

```bash
docker run --rm quickfoods-delivery-model:0.1 \
--distance_km 4.2 \
--items_count 3 \
--is_peak_hour 1 \
--traffic_level 2
```

## Expected Output

```json
{
  "input": {
    "distance_km": 4.2,
    "items_count": 3,
    "is_peak_hour": 1,
    "traffic_level": 2
  },
  "prediction": {
    "delivery_time_min": 39.39
  }
}
```

## Learning Outcomes

* Create a Dockerfile for ML applications
* Package trained ML models
* Build Docker images with version tags
* Run prediction services in containers
* Understand portable ML deployments




## BY HEMANTH B G   (1BM21SCS04)