# Health Risk Prediction Dashboard with Smart Alerts

A real-time machine learning web application that predicts and classifies individual health risk using medical metrics, an interactive Streamlit dashboard, smart alerts, and MongoDB Atlas persistence.

> **Disclaimer:** This project is for educational and portfolio use only. It is not a substitute for professional medical advice, diagnosis, or treatment.

## Highlights

- Logistic Regression model for binary health risk classification
- Interactive Streamlit dashboard for fast user input and visualization
- Smart alerts based on prediction probability and key medical thresholds
- MongoDB Atlas integration for storing user submissions and predictions
- Feature preprocessing and scaling for stable model performance
- Modular Python source code with tests and clean project structure

## Tech Stack

- Python
- Streamlit
- scikit-learn
- pandas / NumPy
- MongoDB Atlas
- Plotly
- pytest

## Project Structure

```text
health-risk-prediction-dashboard/
├── app/
│   └── streamlit_app.py
├── data/
│   └── sample_health_data.csv              # generated after training
├── docs/
├── models/
│   └── health_risk_model.joblib            # generated after training
├── scripts/
│   └── train_model.py
├── src/
│   ├── alerts.py
│   ├── config.py
│   ├── database.py
│   ├── model.py
│   └── preprocessing.py
├── tests/
│   ├── test_alerts.py
│   └── test_preprocessing.py
├── .env.example
├── .gitignore
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── requirements.txt
```

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/health-risk-prediction-dashboard.git
cd health-risk-prediction-dashboard
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv

# macOS/Linux
source .venv/bin/activate

# Windows
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

```bash
cp .env.example .env
```

Update `.env` with your MongoDB Atlas connection string:

```env
MONGODB_URI=mongodb+srv://<username>:<password>@<cluster-url>/<database>?retryWrites=true&w=majority
MONGODB_DATABASE=health_risk_dashboard
MONGODB_COLLECTION=predictions
MODEL_PATH=models/health_risk_model.joblib
```

MongoDB is optional for local testing. If it is not configured, the dashboard still runs but does not persist predictions.

## Training the Model

Train the Logistic Regression model and generate sample data:

```bash
python scripts/train_model.py
```

This creates:

- `data/sample_health_data.csv`
- `models/health_risk_model.joblib`

## Running the Dashboard

```bash
streamlit run app/streamlit_app.py
```

Open the local Streamlit URL in your browser, enter health metrics, and click **Predict Health Risk**.

## Usage Example

Example input values:

```text
Age: 52
Systolic BP: 145
Diastolic BP: 92
Glucose: 135
Cholesterol: 245
BMI: 31.2
```

Example output:

```text
Risk Class: High Risk
Risk Probability: 78.4%
Smart Alerts:
- Critical: predicted risk probability is high.
- Blood pressure is above the common hypertension threshold.
- Glucose level is elevated and may require medical review.
```

## Testing

```bash
pytest
```

## Model Notes

The included training script creates a synthetic dataset for demonstration. For production or research use, replace it with a validated, ethically sourced, privacy-compliant medical dataset.

Reported portfolio metrics such as approximately 87% accuracy and 92% precision should be validated against your final dataset and experiment setup before publication.

## Security and Privacy

- Do not commit `.env` files or credentials.
- Use MongoDB Atlas network access controls.
- Avoid storing personally identifiable health information unless required and compliant with applicable laws.
- Apply encryption, access control, audit logging, and consent workflows for production use.

## Roadmap

- Add authentication
- Add role-based access control
- Add historical prediction analytics
- Add model monitoring and drift detection
- Add Docker deployment
- Add CI/CD deployment workflow

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting a pull request.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
