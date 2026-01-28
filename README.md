# Fake Job Post Detective

> **An AI-powered web application that helps job seekers identify fraudulent job postings using machine learning**

[![Machine Learning](https://img.shields.io/badge/ML-Ensemble%20Models-blue)](https://github.com/ndtkhang/fake_job_post_detective)
[![ROC-AUC](https://img.shields.io/badge/ROC--AUC-97%25-success)](https://github.com/ndtkhang/fake_job_post_detective)
[![T3 Stack](https://img.shields.io/badge/Built%20with-T3%20Stack-blueviolet)](https://create.t3.gg/)
[![FastAPI](https://img.shields.io/badge/API-FastAPI-009688)](https://fastapi.tiangolo.com/)

---

##  Demo Video

> *Click below to watch our application in action*

[![Fake Job Post Detective Demo](https://img.youtube.com/vi/99kwZoZyrbc/maxresdefault.jpg)](https://youtu.be/99kwZoZyrbc)

---

##  Project Overview

**Fake Job Post Detective** is a full-stack machine learning application developed for **CS 5821 Machine Learning** that detects fraudulent job postings with **97% accuracy**. The system combines advanced ensemble ML models with an intuitive web interface to protect job seekers from scams.

###  Key Features

-  **High-Performance ML Model** - Voting ensemble (Gradient Boosting + XGBoost + LightGBM) achieving 0.9709 ROC-AUC
-  **Real-Time Predictions** - FastAPI backend with ~200ms response time
-  **Modern UI** - Clean, responsive interface built with React and TailwindCSS
-  **Intelligent Parser** - Automatically extracts and formats job posting data
-  **Confidence Scoring** - Provides probability scores and explanations for each prediction

---

##  Architecture

```
┌─────────────────┐      ┌──────────────────┐      ┌─────────────────────┐
│   Web Frontend  │ ───▶ │   FastAPI Server │ ───▶ │  ML Voting Ensemble │
│   (T3 Stack)    │ ◀─── │   (REST API)     │ ◀─── │   (97% ROC-AUC)     │
└─────────────────┘      └──────────────────┘      └─────────────────────┘
         │                        │                           │
         │                        │                           │
    User Input              Preprocessing              Model Inference
  (Copy/Paste Job)      (TF-IDF + SVD + Scaler)   (GB + XGB + LGBM)
```

---

##  Tech Stack

### Frontend
- [Next.js](https://nextjs.org) - React framework with server-side rendering
- [TypeScript](https://www.typescriptlang.org/) - Type-safe JavaScript
- [Tailwind CSS](https://tailwindcss.com) - Utility-first CSS framework
- [tRPC](https://trpc.io) - End-to-end typesafe APIs
- [Shadcn UI](https://ui.shadcn.com/) - Beautiful, accessible components

### Backend & ML
- [FastAPI](https://fastapi.tiangolo.com/) - High-performance Python API framework
- [scikit-learn](https://scikit-learn.org/) - Machine learning library
- [XGBoost](https://xgboost.readthedocs.io/) - Gradient boosting framework
- [LightGBM](https://lightgbm.readthedocs.io/) - Fast gradient boosting
- [Uvicorn](https://www.uvicorn.org/) - Lightning-fast ASGI server

### Development Tools
- [Prisma](https://prisma.io) - Next-generation ORM
- [Zod](https://zod.dev/) - TypeScript-first schema validation
- Git & GitHub - Version control and collaboration

---

## Installation & Setup

### Prerequisites
- Node.js 18+ and npm/pnpm
- Python 3.9+
- Git

### Clone the Repository
```bash
git clone https://github.com/rednaksiii/fake_job_post_detective.git
cd fake_job_post_detective
```

### Install Frontend Dependencies
```bash
npm install
# or
pnpm install
```

###  Set Up Environment Variables
```bash
cp .env.example .env
```

Edit `.env` and add your configuration:
```env
DATABASE_URL="your-database-url"
NEXTAUTH_SECRET="your-secret-key"
NEXTAUTH_URL="http://localhost:3000"
API_URL="http://localhost:8000"
```

###  Run Database Migrations
```bash
npx prisma migrate dev
npx prisma generate
```

###  Start the Development Server
```bash
npm run dev
# or
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser 🎉

---

##  ML Model Setup

### Install Python Dependencies
```bash
pip install fastapi uvicorn scikit-learn xgboost lightgbm joblib pandas numpy
```

### Run the FastAPI Server
```bash
cd api
uvicorn app:app --reload --port 8000
```

API Documentation: [http://localhost:8000/docs](http://localhost:8000/docs)

---

## Model Performance

| Metric | Score |
|--------|-------|
| **ROC-AUC** | **0.9709** (97.09%) |
| **Accuracy** | 97.2% |
| **Fake Job Recall** | 77.3% |
| **Precision** | High |

*Significantly exceeds typical fraud detection benchmarks (70-80%) by 24%*

### Feature Importance
-  **has_company_logo**: 28.4%
- Text-derived features (TF-IDF + SVD)
-  Employment type, experience, education

---



---

##  Documentation

- Project Report - Detailed technical report
- [API Documentation](http://localhost:8000/docs) - FastAPI Swagger UI
- [T3 Stack Docs](https://create.t3.gg/) - Framework documentation

---

##  Development Workflow

### Branch Strategy
- `main` - Production-ready releases
- `development` - Pre-release testing
- `<name>-<feature>` - Feature development (e.g., `jin-parser`)

### Deployment Stages
1. **Mock** - Frontend mockups + parser prototype
2. **First Integration** - Parser → Frontend pipeline
3. **Second Integration** - FastAPI → Full stack integration

---

## Deployment

### Local Deployment Only
Due to resource constraints, this project runs locally. To test:

– Follow installation steps above for local setup

### Production Deployment (Future)
Follow deployment guides for:
- [Vercel](https://create.t3.gg/en/deployment/vercel) - Frontend hosting
- [Railway](https://railway.app/) or [Render](https://render.com/) - API hosting
- [Docker](https://create.t3.gg/en/deployment/docker) - Containerization

---

##  License

This project was created for educational purposes as part of CS 5821 Machine Learning course.

---

## Acknowledgments

- **Dataset**: [Real or Fake Job Posting Prediction](https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction) by Shivam Bansal
- **Framework**: [T3 Stack](https://create.t3.gg/) by Theo Browne
- **Course**: CS 5821 Machine Learning
