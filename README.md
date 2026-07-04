# 🚗 Car Price Prediction App

A machine learning-powered web application that predicts car prices using XGBoost. This project combines Jupyter notebooks for data exploration and model training with a Flask web application for deployment.

## 📋 Features

- **Machine Learning Model**: XGBoost-based price prediction model
- **Web Interface**: Flask-based REST API for making predictions
- **Data Processing**: Pandas and NumPy for data manipulation
- **Containerized Deployment**: Docker support for easy deployment
- **Production Ready**: Gunicorn WSGI server for serving the application

## 🏗️ Project Structure

```
car-price-predict-app/
├── notebooks/          # Jupyter notebooks for EDA and model development
├── apps/               # Flask application code
│   └── flask_app.py   # Main Flask application
├── models/             # Trained ML models
│   └── xgb_car_price_model.pkl  # Serialized XGBoost model
├── data/               # Dataset files
├── scripts/            # Utility scripts
├── tests/              # Unit tests
├── Dockerfile          # Docker configuration for containerization
├── requirements.txt    # Python dependencies
├── requirements-dev.txt # Development dependencies
└── .pylintrc          # Python linting configuration
```

## 🛠️ Tech Stack

- **Python 3.13**
- **Machine Learning**: XGBoost, Scikit-learn
- **Web Framework**: Flask
- **Data Processing**: Pandas, NumPy, SciPy
- **Server**: Gunicorn
- **Containerization**: Docker

## 📦 Dependencies

Key dependencies include:
- `flask==3.1.3` - Web framework
- `xgboost==3.2.0` - Machine learning model
- `pandas==3.0.3` - Data manipulation
- `numpy==2.4.6` - Numerical computing
- `gunicorn==26.0.0` - Production WSGI server
- `scipy==1.17.1` - Scientific computing

See `requirements.txt` for the complete list of dependencies.

## 🚀 Getting Started

### Prerequisites
- Python 3.13+
- Docker (optional, for containerized deployment)

### Local Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/tarini-py/car-price-predict-app.git
   cd car-price-predict-app
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Flask application**
   ```bash
   python apps/flask_app.py
   ```

The application will be available at `http://localhost:5000`

### Docker Deployment

1. **Build the Docker image**
   ```bash
   docker build -t car-price-predict-app .
   ```

2. **Run the container**
   ```bash
   docker run -p 80:5000 car-price-predict-app
   ```

   For production with multiple workers:
   ```bash
   docker run -p 80:5000 -e WORKERS=5 car-price-predict-app
   ```

The application will be accessible at `http://localhost`

## 📊 Model Development

The project includes Jupyter notebooks in the `notebooks/` directory for:
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Model Training & Evaluation
- Model Validation

To run the notebooks:
```bash
pip install jupyter
jupyter notebook
```

## 🧪 Testing

Run tests using:
```bash
pytest tests/
```

For linting:
```bash
pylint apps/
```

## 📝 Development

Install development dependencies:
```bash
pip install -r requirements-dev.txt
```

## 🐳 Docker Configuration

The Dockerfile uses:
- Base image: `python:3.13-slim`
- Production server: Gunicorn with configurable workers
- Exposed port: 80

Default configuration runs with 1 worker but can be scaled horizontally using the `WORKERS` environment variable.

## 📄 License

This project is open source and available under the MIT License.

## 👤 Author

[tarini-py](https://github.com/tarini-py)

---

**Note**: This is a machine learning application. For production use, ensure:
- The model file is properly serialized and version-controlled
- Input validation is implemented
- Error handling is robust
- Performance monitoring is in place
