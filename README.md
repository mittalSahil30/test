# test

# 🧠 Mental Health Chatbot - AI-Powered Mental Wellness Assistant

![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)
![Flask](https://img.shields.io/badge/flask-2.0%2B-green)
![License](https://img.shields.io/badge/license-MIT-orange)
![Status](https://img.shields.io/badge/status-active-success)

A comprehensive mental health support application that leverages machine learning and natural language processing to provide mental wellness education, self-assessment tools, and supportive resources. This chatbot is designed to raise awareness about mental health and offer guided support through various interactive features.

![Application Screenshot](screenshots/main-interface.png)

---

## 👥 Project Team

| Name | Student ID |
|------|-----------|
| Your Name | 23106045 |

---

## 📋 Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Technology Stack](#technology-stack)
- [System Architecture](#system-architecture)
- [Installation Guide](#installation-guide)
- [Configuration](#configuration)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Machine Learning Model](#machine-learning-model)
- [Screenshots](#screenshots)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

---

## 🎯 Overview

The Mental Health Chatbot is an intelligent web application designed to provide accessible mental health education and support. Built with Python and powered by machine learning, this platform offers a safe, private space for users to learn about mental health, engage in self-reflection through journaling, practice mindfulness, and access emergency resources.

**Important Note:** This application is designed for educational purposes and mental wellness support. It is NOT a diagnostic tool and should not replace professional mental health services.

### Project Goals

- 🎓 **Educate** users about various mental health topics
- 💬 **Provide** conversational AI support through an intelligent chatbot
- 📊 **Enable** self-assessment through mental health screening tests
- 🧘 **Promote** mindfulness and wellness practices
- 📝 **Facilitate** self-reflection through journaling features
- 🆘 **Connect** users with emergency mental health resources

---

## ✨ Key Features

### 1. **Intelligent Conversational AI**
- Natural language processing-powered chatbot
- Topic-specific conversations about mental health
- Context-aware responses using TensorFlow and NLTK
- Educational content delivery through interactive dialogue

![Chatbot Interface](screenshots/chatbot-conversation.png)

### 2. **User Authentication & Privacy**
- Secure user registration and login system
- Guest mode for anonymous access
- Password encryption using Flask-Bcrypt
- Session management with Flask-Login
- Privacy-focused design

![Login Screen](screenshots/login-page.png)

### 3. **Mental Health Assessment**
- Standardized mental health screening questionnaires
- Instant results and recommendations
- Progress tracking over time
- Educational insights based on assessment results

![Assessment Tool](screenshots/mental-health-test.png)

### 4. **Mindfulness & Wellness Exercises**
- Guided meditation sessions
- Breathing exercises
- Relaxation techniques
- Stress management tools
- Audio/visual guidance for mindfulness practices

![Mindfulness Exercises](screenshots/mindfulness-section.png)

### 5. **Personal Journaling**
- Private journal entries for self-reflection
- Mood tracking capabilities
- Date-stamped entries
- Secure storage in MySQL database
- Search and filter functionality

![Journal Feature](screenshots/journal-interface.png)

### 6. **Emergency Resources**
- Quick access to mental health hotlines
- Crisis support contact information
- Regional emergency services (Currently Malaysia-focused)
- Resource library for immediate help

![SOS Hotline](screenshots/sos-hotline.png)

### 7. **User Profile Management**
- Customizable user profiles
- Activity history
- Preferences and settings
- Account management tools

![User Profile](screenshots/user-profile.png)

---

## 🛠️ Technology Stack

### Frontend
- **Python** - Core programming language
- **Flask** - Web application framework
- **Bootstrap 5** - Responsive UI framework
- **Jinja2** - Template engine
- **HTML5/CSS3** - Markup and styling
- **JavaScript** - Interactive elements

### Backend
- **Python 3.8+** - Server-side logic
- **Flask** - RESTful API and routing
- **SQLAlchemy** - ORM for database operations
- **Flask-Login** - User session management
- **Flask-Bcrypt** - Password hashing

### Database
- **MySQL** - Relational database management
- **SQLAlchemy ORM** - Database abstraction layer

### Machine Learning & NLP
- **TensorFlow** - Deep learning framework
- **NLTK** (Natural Language Toolkit) - Text processing
- **NumPy** - Numerical computations
- **Scikit-learn** - ML utilities

### Additional Libraries
- **Flask-WTF** - Form handling and validation
- **Flask-Migrate** - Database migrations
- **Python-dotenv** - Environment variable management

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    User Interface (Web)                  │
│                  Bootstrap + Jinja2 Templates            │
└────────────────────────┬────────────────────────────────┘
                         │
┌────────────────────────▼────────────────────────────────┐
│                    Flask Application                     │
│  ┌──────────────┬──────────────┬──────────────────────┐ │
│  │   Routes &   │  Business    │   Authentication     │ │
│  │   Views      │  Logic       │   & Authorization    │ │
│  └──────────────┴──────────────┴──────────────────────┘ │
└────────────────────────┬────────────────────────────────┘
                         │
         ┌───────────────┼───────────────┐
         │               │               │
┌────────▼────────┐ ┌───▼────────┐ ┌───▼─────────────┐
│   SQLAlchemy    │ │ ML Model   │ │  NLTK Text     │
│   ORM Layer     │ │ TensorFlow │ │  Processing    │
└────────┬────────┘ └────────────┘ └────────────────┘
         │
┌────────▼────────┐
│  MySQL Database │
│  - Users        │
│  - Journals     │
│  - Assessments  │
└─────────────────┘
```

---

## 📥 Installation Guide

### Prerequisites

Before you begin, ensure you have the following installed:
- Python 3.8 or higher
- MySQL Server 5.7+
- pip (Python package manager)
- Git

### Step 1: Clone the Repository

```bash
git clone https://github.com/TheanYeeSin/Python-Mental-Health-Chatbot.git
cd Python-Mental-Health-Chatbot
```

### Step 2: Set Up Virtual Environment (Recommended)

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Database Setup

1. Create a MySQL database:
```sql
CREATE DATABASE mental_health_chatbot;
```

2. Update database configuration in `config.py`

### Step 5: Configure Application

Edit the `config.py` file with your specific settings:
- Database URI
- Secret keys
- Application settings

### Step 6: Initialize Database

```bash
flask db init
flask db migrate
flask db upgrade
```

### Step 7: Run the Application

```bash
python run.py
```

The application will be accessible at `http://localhost:5000`

---

## ⚙️ Configuration

Create or modify the `config.py` file in the root directory:

```python
import os

class Config:
    # Secret key for session management
    SECRET_KEY = os.environ.get('SECRET_KEY') or 'your-secret-key-here'
    
    # Database configuration
    SQLALCHEMY_DATABASE_URI = 'mysql+pymysql://username:password@localhost/mental_health_chatbot'
    SQLALCHEMY_TRACK_MODIFICATIONS = False
    
    # Application settings
    DEBUG = False
    TESTING = False
    
    # Upload settings (if applicable)
    MAX_CONTENT_LENGTH = 16 * 1024 * 1024  # 16MB max file size

class DevelopmentConfig(Config):
    DEBUG = True

class ProductionConfig(Config):
    DEBUG = False
```

### Environment Variables

Create a `.env` file in the root directory:

```env
FLASK_APP=run.py
FLASK_ENV=development
SECRET_KEY=your-secret-key
DATABASE_URL=mysql+pymysql://username:password@localhost/mental_health_chatbot
```

---

## 🚀 Usage

### Running the Application

```bash
python run.py
```

### Accessing the Application

1. Open your web browser
2. Navigate to `http://localhost:5000`
3. Choose to register, login, or continue as guest

### Using the Chatbot

1. Navigate to the chatbot interface
2. Select a specific mental health topic or start a general conversation
3. Type your questions or concerns
4. Receive AI-powered responses with educational content

![Chatbot Usage](screenshots/chatbot-demo.png)

### Taking Mental Health Assessments

1. Go to the "Mental Health Test" section
2. Answer the questionnaire honestly
3. Submit your responses
4. Review your results and recommendations

### Journaling

1. Access the journaling feature from the navigation menu
2. Create new entries to record your thoughts and feelings
3. View previous entries to track your mental wellness journey

### Mindfulness Exercises

1. Select the "Mindfulness" section
2. Choose from various exercises
3. Follow guided instructions
4. Practice regularly for best results

---

## 📁 Project Structure

```
Python-Mental-Health-Chatbot/
│
├── app/
│   ├── __init__.py           # Application factory
│   ├── models.py             # Database models
│   ├── routes.py             # URL routes and views
│   ├── forms.py              # WTForms definitions
│   ├── chatbot.py            # Chatbot logic
│   │
│   ├── static/
│   │   ├── css/              # Stylesheets
│   │   ├── js/               # JavaScript files
│   │   ├── images/           # Image assets
│   │   └── models/           # ML model files
│   │
│   └── templates/
│       ├── base.html         # Base template
│       ├── index.html        # Home page
│       ├── chat.html         # Chatbot interface
│       ├── journal.html      # Journaling page
│       ├── mindfulness.html  # Mindfulness exercises
│       ├── test.html         # Mental health test
│       └── sos.html          # Emergency resources
│
├── migrations/               # Database migrations
├── venv/                     # Virtual environment
├── config.py                 # Configuration settings
├── requirements.txt          # Python dependencies
├── run.py                    # Application entry point
├── .env                      # Environment variables
├── .gitignore               # Git ignore rules
└── README.md                # This file
```

---

## 🤖 Machine Learning Model

### Model Architecture

The chatbot uses a neural network model built with TensorFlow for intent classification:

- **Input Layer**: Tokenized and vectorized text input
- **Hidden Layers**: Dense layers with ReLU activation
- **Dropout Layers**: Regularization to prevent overfitting
- **Output Layer**: Softmax activation for intent classification

### Training Data

The model is trained on a curated dataset of mental health-related conversations, including:
- Common mental health questions
- Symptom descriptions
- Support-seeking phrases
- Educational queries

### Natural Language Processing

NLTK is used for:
- Text tokenization
- Stopword removal
- Lemmatization
- Feature extraction

### Model Performance

![Model Accuracy](screenshots/model-performance.png)

---

## 📸 Screenshots

### Dashboard
![Dashboard](screenshots/dashboard.png)

### Chat Interface
![Chat Interface](screenshots/chat-full.png)

### Mental Health Assessment
![Assessment](screenshots/assessment-page.png)

### Journal Entries
![Journal](screenshots/journal-entries.png)

### Mindfulness Center
![Mindfulness](screenshots/mindfulness-center.png)

### Emergency Resources
![Emergency](screenshots/emergency-resources.png)

---

## 🔮 Future Enhancements

- [ ] Multi-language support for global accessibility
- [ ] Mobile application (iOS and Android)
- [ ] Integration with wearable devices for mood tracking
- [ ] Advanced sentiment analysis
- [ ] Therapist connection feature
- [ ] Group support forums
- [ ] Expanded emergency resources for multiple countries
- [ ] Voice-based interaction
- [ ] Progressive Web App (PWA) capabilities
- [ ] AI-powered mood prediction
- [ ] Integration with calendar for mindfulness reminders
- [ ] Export journal entries as PDF
- [ ] Data visualization for mental health trends

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Code Style

- Follow PEP 8 guidelines for Python code
- Write clear, descriptive commit messages
- Add comments for complex logic
- Update documentation as needed

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **TensorFlow Team** - For the amazing deep learning framework
- **NLTK Contributors** - For comprehensive NLP tools
- **Flask Community** - For the lightweight and powerful web framework
- **Bootstrap Team** - For the responsive UI components
- **Mental Health Organizations** - For providing educational resources and guidelines
- **Open Source Community** - For inspiration and support

---

## 📞 Contact & Support

For questions, suggestions, or support:

- **Project Repository**: [GitHub Repository](https://github.com/TheanYeeSin/Python-Mental-Health-Chatbot)
- **Issue Tracker**: [GitHub Issues](https://github.com/TheanYeeSin/Python-Mental-Health-Chatbot/issues)

---

## ⚠️ Disclaimer

**This application is for educational and informational purposes only.** It is not intended to be a substitute for professional medical advice, diagnosis, or treatment. Always seek the advice of qualified health providers with any questions you may have regarding mental health conditions.

If you are experiencing a mental health crisis, please contact emergency services or a mental health crisis hotline immediately.

---

## 📊 Project Statistics

- **Development Duration**: Academic Project
- **Primary Language**: Python
- **Framework**: Flask
- **Database**: MySQL
- **ML Framework**: TensorFlow
- **Lines of Code**: ~5000+
- **Contributors**: 1+

---

<div align="center">

**Made with ❤️ for Mental Health Awareness**

⭐ Star this repository if you find it helpful!

</div>
