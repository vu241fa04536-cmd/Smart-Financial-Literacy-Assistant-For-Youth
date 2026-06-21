# 💰 SmartVault — Smart Financial Literacy Assistant
 
**Your AI-Powered Financial Mentor for Young Professionals**
 
SmartVault is a full-stack, AI-powered personal finance platform that helps youth and young professionals track spending, plan budgets, predict savings, and build better money habits — all backed by trained machine learning models, not just static rules.
 
🔗 **Live Demo:** [aipowerfinance.netlify.app](https://aipowerfinance.netlify.app/)
 
---
 
## 📖 About
 
Most young people aren't taught how to manage money — they figure it out (often the hard way) on their own. SmartVault closes that gap by combining everyday expense tracking with real ML-driven insights: spotting unusual spending behavior, recommending budgets based on income and goals, predicting monthly savings, and teaching financial concepts through bite-sized, interactive lessons.
 
It's built as three cooperating layers — a React frontend, a Node.js/Express API, and a Python ML microservice — so the trained models stay decoupled from the web app logic.
 
---
 
## ✨ Features
 
### 🔐 Authentication
- Secure email/password **Login & Registration**
- Persistent logged-in sessions (shown as `@username` in the sidebar)
### 📊 Smart Financial Dashboard
- **Available Cash Right Now** — live snapshot of Bank Balance + Income − Expenses
- **Critical balance alerts** (e.g. "You're out of cash! Add income urgently or stop spending")
- **Spending Analysis** — Daily Burn Rate vs. a calculated Safe Daily Limit
- **Projected Month-End Savings** with progress visualization
- **Safe-to-Spend buffer** (70% spend / 30% emergency buffer rule)
### 💸 Expense Tracker
- Quick Add for **Income** and **Expense** transactions
- Categorized spending: Food, Transport, Entertainment, Shopping, Education, Rent, Misc
- **Category Breakdown** view comparing actual spend per category
- Budget-vs-actual comparison once a monthly budget is set
### 🤖 AI-Powered Insights (ML Microservice)
- **Track Spending Habits** — detects unusual/anomalous transactions using a trained anomaly-detection model
- **Predict Monthly Savings** — forecasts savings based on user profile (age, income, bank balance, financial literacy score, saving habit score) using a trained ML model
- **Smart Insights tab** — savings trend chart over time + plain-language spending habit analysis
- **Top Spending Category** detection
### 🧮 Budget Manager
- **Suggest Budgeting Plans** — personalized budget recommendations based on income, expenses, and goals
- Editable user profile (ML inputs): Age, Monthly Income, Bank Balance, Financial Literacy score, Saving Habit score
### 🎯 Financial Goals
- Create and track multiple savings goals
- Dashboard summary: Active Goals, Total Target Amount, Completed Goals
- Visual progress tracking per goal
### 🐷 Piggy Bank (Emergency Fund)
- Dedicated emergency fund tracker with goal progress bar
- "Add Money" and "Emergency withdrawal" actions
- Eligibility status based on current savings rate
### 💬 In-App Financial Assistant (Chatbot)
- Floating chat widget — "Ask me anything about your finances"
- Quick-action prompts: *Can I afford?*, *Piggy Bank status*, *Budget overview*, *Am I overspending?*
- Conversational answers grounded in the user's live financial data
### 📚 Financial Education
- Bite-sized articles, tips, and interactive learning modules
- Designed to build financial literacy alongside hands-on tracking
---
 
## 🛠️ Tech Stack
 
| Layer | Technology |
|---|---|
| **Frontend** | React |
| **Backend API** | Node.js, Express |
| **ML Service** | Python (Flask), scikit-learn |
| **ML Models** | Trained `.pkl` models — anomaly detection, budget recommendation, spending analysis, savings prediction |
| **Containerization** | Docker |
| **Deployment** | Netlify (frontend) · Render (`render.yaml` — backend/ML service) |
 
> 📝 The repo includes pre-trained models (`model.pkl`, `budget_model.pkl`, `anomaly_behavior_model.pkl`, `spending_analysis_model.pkl`) along with training datasets (`financial_behavior_dataset`, `financial_literacy_youth_dataset_10000`) and a `retrain_model` script for retraining as new data comes in.
 
---
 
## 📁 Project Structure
 
```
Smart-Financial-Literacy-Assistant/
├── client/             # React frontend (or 'frontend/' — consolidate to one)
├── frontend/
├── server/             # Node.js + Express API (or 'backend/' — consolidate to one)
├── backend/
├── ml_service/         # Python ML microservice
│   ├── model.pkl
│   ├── budget_model.pkl
│   ├── anomaly_behavior_model.pkl
│   ├── spending_analysis_model.pkl
│   ├── data/
│   ├── retrain_model.py
│   ├── Dockerfile
│   └── render.yaml
└── README.md
```
 

---
 
## 🚀 Getting Started
 
### Prerequisites
- Node.js (v18+)
- npm or yarn
- Python 3.9+
- pip
- Docker (optional, for running the ML service in a container)
### 1. Clone the repository
```bash
git clone https://github.com/vu241fa04536-cmd/Smart-Financial-Literacy-Assistant-For-Youth
cd Smart-Financial-Literacy-Assistant
```
 
### 2. Set up the frontend
```bash
cd client
npm install
npm start
```
 
### 3. Set up the backend
```bash
cd ../backend
npm install
npm run dev
```
 
### 4. Set up the ML service
```bash
cd ../ml_service
pip install -r requirements.txt
python model.py
```
 
Or run the ML service with Docker:
```bash
cd ml_service
docker build -t smartvault-ml .
docker run -p 5000:5000 smartvault-ml
```
 
### 5. Environment Variables
Create a `.env` file in the `backend/` folder:
```env
PORT=5000
DATABASE_URL=your_database_connection_string
JWT_SECRET=your_jwt_secret
ML_SERVICE_URL=http://localhost:5001
```
 
---
 
## 🧠 Machine Learning Models
 
| Model | Purpose |
|---|---|
| `model.pkl` | Core savings prediction model |
| `budget_model.pkl` | Personalized budget recommendation |
| `anomaly_behavior_model.pkl` | Detects unusual/risky spending behavior |
| `spending_analysis_model.pkl` | Category-level spending pattern analysis |
 
Trained on `financial_behavior_dataset` and `financial_literacy_youth_dataset_10000`, with `retrain_model.py` available to retrain on updated data.
 
---
 
## 🗺️ Roadmap
- [ ] Consolidate duplicate frontend/backend folders
- [ ] Add database schema documentation
- [ ] Expand financial education content library
- [ ] Add multi-currency support
- [ ] Mobile app version
---
 

## 👤 Author
## Ranjna Ray
feel free to reach out for questions or collaboration.
 
