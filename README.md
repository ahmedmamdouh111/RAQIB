# RAQIB AI Service

## Overview

RAQIB AI Service is the intelligent core of the RAQIB platform. It is responsible for analyzing uploaded images, detecting urban issues using deep learning, estimating damage severity, and providing structured AI responses to the backend system.

The service exposes RESTful APIs through FastAPI, allowing seamless integration with the ASP.NET Core backend. Once a citizen uploads an image, the AI model processes it and returns the predicted issue type, confidence score, severity level, and damage assessment in real time.

---


## My Contribution

This project was developed as a team project during the DEPI program.

My main contributions included:
- Collecting and organizing disaster-related infrastructure images for the project dataset.
- Reviewing and preparing image data for model training.
- Assisting with deep learning model experiments and performance improvement.
- Contributing to the evaluation and selection of the final image classification model.

---


## Features

- AI-powered urban issue classification
- Image preprocessing and normalization
- Deep Learning inference using TensorFlow
- Severity estimation
- Confidence score generation
- Damage percentage estimation
- REST API built with FastAPI
- Seamless integration with ASP.NET Core
- JSON-based response format
- Optimized for real-time predictions

---

## Supported Urban Issues

The AI model classifies images into the following categories:

- Damaged Road
- Normal Road
- Damaged Building
- Normal Building
- Large Trash
- Small Trash

---

## AI Workflow

1. Receive an image from the backend.
2. Preprocess the image.
3. Resize and normalize input.
4. Run inference using the trained MobileNetV2 model.
5. Predict the issue category.
6. Calculate confidence score.
7. Estimate damage severity.
8. Return the prediction as a JSON response.

---

## Model Architecture

The model is based on Transfer Learning using MobileNetV2.

Architecture:

- MobileNetV2 Backbone
- Global Average Pooling
- Batch Normalization
- Dense Layer
- Dropout
- Output Layer (Softmax)

The model was trained to recognize six different urban issue classes while maintaining fast inference suitable for deployment.

---

## Technologies

### AI & Machine Learning

- Python 3.12
- TensorFlow
- Keras
- MobileNetV2
- NumPy
- Pillow
- OpenCV

### API

- FastAPI
- Uvicorn
- Pydantic

---

## Project Structure

```text
RAQIB_AI/
│
├── app.py
├── predict.py
├── chatbot.py
├── requirements.txt
├── disaster_6class_model_final.keras
├── uploads/
└── utils/
```

---

## API Endpoints

### Health Check

```
GET /
```

Returns the service status.

---

### Predict

```
POST /predict
```

Receives an image and returns:

- Predicted Class
- Confidence Score
- Severity Level
- Severity Score
- Damage Percentage
- AI Response

---

## Installation

Clone the repository

```bash
git clone https://github.com/your-username/RAQIB_AI.git
```

Navigate to the project directory

```bash
cd RAQIB_AI
```

Create a virtual environment

```bash
python -m venv venv
```

Activate the environment

Windows

```bash
venv\Scripts\activate
```

Linux / macOS

```bash
source venv/bin/activate
```

Install dependencies

```bash
pip install -r requirements.txt
```

Run the server

```bash
uvicorn app:app --reload
```

The API will be available at:

```
http://127.0.0.1:8000
```

---

## Integration

The AI service is consumed by the ASP.NET Core backend.

Workflow:

Citizen → Frontend → ASP.NET Core API → FastAPI AI Service → Prediction → ASP.NET Core → Database → Frontend

---

## Performance

- Real-time inference
- Lightweight deployment
- Optimized MobileNetV2 architecture
- Fast API response
- High prediction accuracy

---

## Future Improvements

- Object Detection
- Image Segmentation
- Multi-label Classification
- Automatic Damage Localization
- Continuous Model Retraining

---

# RAQIB Frontend

## Overview

RAQIB is the frontend application of an AI-powered Smart Urban Issue Detection and Reporting System. It provides an intuitive interface that enables citizens to report urban issues such as damaged roads, unsafe buildings, and waste accumulation by uploading images and specifying their locations. The system communicates with an AI-powered backend to analyze reports, assess their severity, and prioritize critical cases for faster response.

The platform also provides administrators with a comprehensive dashboard for monitoring reports, managing their status, and visualizing incidents on an interactive map. In addition, users can communicate with an AI chatbot to receive guidance, safety recommendations, and real-time updates about their submitted reports.

---

## Features

### Citizen Features

- Secure user authentication
- Email verification using OTP
- Image upload for issue reporting
- Automatic and manual location selection
- Interactive map integration
- AI-generated issue analysis
- Real-time report tracking
- AI chatbot assistance
- Instant notifications
- User profile management

### Administrator Features

- Dashboard for monitoring reports
- Interactive map displaying reported issues
- Report management and status updates
- Priority-based monitoring of critical reports
- Real-time notifications using SignalR

---

## Technologies

### Frontend

- React.js
- Vite
- React Router DOM
- Axios
- SignalR Client
- React Leaflet
- Framer Motion
- CSS3

### Backend Integration

The frontend communicates with:

- ASP.NET Core Web API
- FastAPI AI Service
- SQL Server Database

---

## Project Structure

```text
src/
│
├── assets/
├── components/
├── pages/
├── services/
├── hooks/
├── styles/
├── utils/
├── App.jsx
└── main.jsx
```

---

## Installation

Clone the repository

```bash
git clone https://github.com/your-username/RAQIB_FRONTEND.git
```

Navigate to the project directory

```bash
cd RAQIB_FRONTEND
```

Install dependencies

```bash
npm install
```

Start the development server

```bash
npm run dev
```

Build the project

```bash
npm run build
```

---

## Main Modules

- Authentication
- User Dashboard
- Report Submission
- Interactive Map
- AI Chatbot
- Notifications
- Report Details
- User Profile
- Admin Dashboard
- Reports Management

---
# RAQIB Backend API

<div align="center">


Backend built with **ASP.NET Core Web API**

</div>

---

## ✨ Features

### 🔐 Authentication & Authorization

- Email Sign Up
- Secure Login
- JWT Authentication
- Google OAuth Authentication
- OTP Email Verification
- Forgot Password
- Password Reset
- Role-Based Authorization (Citizen / Admin)

---

### 👤 Citizen Features

- Create Reports
- Upload Images
- GPS Location Support
- Track Report Status
- View Report History
- Interactive Map
- AI Chat History
- Real-Time Notifications
- Email Notifications

---

### 🏛️ Admin Features

- Manage Reports
- Update Report Status
- Approve / Reject Reports
- Severity-Based Prioritization
- User Management
- Interactive Dashboard
- Charts & Statistics
- Governorate & Date Filtering
- PDF Analytics Reports

---

### 🤖 AI Integration

The backend communicates with a dedicated FastAPI AI service responsible for:

- Image Classification
- Confidence Score Prediction
- Severity Assessment
- Arabic AI Assistant Integration

The backend stores AI results and connects them with citizen reports.

---

### 🔔 Notification System

The system provides real-time communication using:

- SignalR
- Email Notifications
- Live Report Status Updates

Whenever a report status changes, the citizen instantly receives:

- In-App Notification
- Email Notification

---

### 📊 Analytics

Administrators can access:

- Dashboard Statistics
- Reports by Governorate
- Reports by Category
- Severity Distribution
- Date Filtering
- PDF Report Generation

---

## 🧠 AI Categories

The current version supports six categories:

- Damaged Road
- Normal Road
- Damaged Home
- Normal Building
- Big Trash
- Small Trash

Future versions can easily support additional categories.

---

## 🏗️ Architecture

The backend follows **Clean Architecture**.

```
Presentation Layer
        │
Controllers
        │
Application Layer
        │
Business Logic
        │
Infrastructure Layer
        │
Repositories
        │
Entity Framework Core
        │
SQL Server
```

---

## 🛠️ Technology Stack

### Backend

- ASP.NET Core Web API
- C#
- Entity Framework Core
- SQL Server
- AutoMapper
- FluentValidation

### Authentication

- JWT
- Google OAuth
- OTP Email Verification

### AI Integration

- FastAPI
- REST API

### Communication

- SignalR
- MailKit

### Documentation

- Swagger / OpenAPI

### Reports

- QuestPDF

---

## 📂 Project Structure

```
RAQIB_API
│
├── RAQIB.API
├── RAQIB.Application
├── RAQIB.Core
├── RAQIB.Infrastructure
│
├── Controllers
├── Services
├── Repositories
├── DTOs
├── Entities
├── Interfaces
├── SignalR
├── Middleware
└── Helpers
```

---

## 🚀 Running the Project

### Clone

```bash
git clone https://github.com/RAQIB26/your-backend-repo.git
```

### Restore Packages

```bash
dotnet restore
```

### Update Database

```bash
dotnet ef database update
```

### Run

```bash
dotnet run
```

Swagger

```
https://localhost:{PORT}/swagger
```

---

## 🔄 System Workflow

1. User registers or logs in.
2. User uploads an image and GPS location.
3. Backend stores the report.
4. Backend sends the image to the FastAPI AI Service.
5. AI returns:
   - Classification
   - Confidence Score
   - Severity Level
6. Backend saves prediction results.
7. Admin reviews the report.
8. Status updates trigger:
   - SignalR Notifications
   - Email Notifications
9. User tracks progress from the dashboard.

---

## 📈 Highlights

- Clean Architecture
- Repository Pattern
- Dependency Injection
- JWT Authentication
- Google OAuth
- OTP Verification
- SignalR Real-Time Communication
- AI Integration
- PDF Report Generation
- Interactive Dashboard
- RESTful APIs
- Scalable Design

---
## Developed By

- Zyad Atef
- Manal Mahmoud
- Nourhan Hamada
- Hager Zakaria
- Ahmed Mamdouh
- Abdallah Kamel

## 👨‍💻 Author

**Zyad Atef**

Backend Developer & Team Leader

Faculty of Computers & Artificial Intelligence, Cairo University

---

## 📄 License

This project was developed as part of the **RAQIB Graduation Project**.

## Project Objective

RAQIB aims to simplify the process of reporting urban issues by combining Artificial Intelligence, real-time communication, and interactive mapping into a single platform. The system enhances collaboration between citizens and local authorities, helping improve response time, prioritize high-risk incidents, and support the development of safer and smarter cities.

---
