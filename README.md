# DigiVote

> **Empowering Secure, Transparent, and Seamless Voting Experiences**

<p align="center">
  <img src="https://img.shields.io/badge/Python-blue?logo=python" />
  <img src="https://img.shields.io/badge/Flask-black?logo=flask" />
  <img src="https://img.shields.io/badge/TensorFlow-orange?logo=tensorflow" />
  <img src="https://img.shields.io/badge/Firebase-orange?logo=firebase" />
  <img src="https://img.shields.io/badge/Docker-blue?logo=docker" />
  <img src="https://img.shields.io/badge/NumPy-teal?logo=numpy" />
  <img src="https://img.shields.io/badge/SciPy-lightblue?logo=scipy" />
  <img src="https://img.shields.io/badge/Gunicorn-green?logo=gunicorn" />
</p>

---

## 📖 Table of Contents

* [Overview](#-overview)
* [Key Features](#-key-features)
* [Biometric Authentication Pipeline](#-biometric-authentication-pipeline)
* [Project Structure](#-project-structure)
* [Getting Started](#-getting-started)
  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
* [Security](#-security)
* [Future Improvements](#-future-improvements)

---

## 🚀 Overview

**DIGIVOTE** is a biometric e-voting platform designed to provide secure and transparent digital voting through **facial recognition, deep-learning-based face embeddings, Firebase services, and a Flask backend**.

The project combines biometric voter verification with cloud-backed authentication, election management, administrative workflows, and containerized deployment.

The central idea is to use a biometric identity-verification layer before giving an authenticated voter access to the voting workflow.

### Core Components

* 🧠 **Biometric Authentication** — Facial recognition and verification using deep-learning-based face embeddings.
* 🔐 **Secure Backend** — Flask-based application endpoints and authentication workflows.
* ☁️ **Cloud Services** — Firebase Authentication, Firestore, and Storage for application data and user management.
* 🐳 **Containerized Deployment** — Docker support for consistent application environments.
* 🎯 **Voting Workflow** — Voter registration, biometric verification, voting, and result visualization.
* ⚙️ **Administration** — Administrative dashboards and election-management functionality.
* 🎨 **User Interface** — Web templates for voters and administrators.

---

## ✨ Key Features

### 🧑‍💻 Biometric Voter Verification

The platform uses facial recognition to verify the identity of registered voters before they access the voting workflow.

The face-processing pipeline includes:

* Face detection
* Face cropping and preprocessing
* Face embedding generation
* Embedding-based identity verification
* Voter authentication

### 🔒 Authentication & Access Control

Firebase services are used to support:

* User authentication
* Role-based access
* Voter management
* Administrative workflows
* Persistent election data

### 🗳️ Election Management

Administrative functionality supports election-related operations such as:

* Voter registration
* Voter verification
* Election management
* Administrative oversight
* Result visualization

### ☁️ Firebase Integration

The application uses Firebase as part of its cloud infrastructure:

* **Firebase Authentication** — User authentication and identity management
* **Cloud Firestore** — Structured application and election data
* **Firebase Storage** — Storage for application files and biometric-related assets

### 🐳 Dockerized Deployment

The project includes Docker configuration so the application can be packaged and deployed using a consistent runtime environment.

### ⚙️ Flask Backend

Flask provides the backend application layer and handles application routes, authentication-related workflows, voter operations, and administrative functionality.

---

## 🏗️ System Architecture

```text
                         +----------------------+
                         |       User           |
                         |   Voter / Admin      |
                         +----------+-----------+
                                    |
                                    v
                         +----------------------+
                         |    Flask Web App     |
                         +----------+-----------+
                                    |
                 +------------------+------------------+
                 |                  |                  |
                 v                  v                  v
        +----------------+  +---------------+  +---------------+
        | Face           |  | Firebase Auth |  | Admin /       |
        | Verification   |  |               |  | Election      |
        +-------+--------+  +-------+-------+  | Workflows     |
                |                   |           +-------+-------+
                v                   |                   |
        +----------------+          |                   |
        | Face Detection |          |                   |
        | + Embeddings   |          |                   |
        +-------+--------+          |                   |
                |                   |                   |
                +-------------------+-------------------+
                                    |
                                    v
                         +----------------------+
                         |     Firestore        |
                         |      Storage         |
                         +----------+-----------+
                                    |
                                    v
                         +----------------------+
                         | Voting / Results     |
                         +----------------------+
```

---

## 🧠 Biometric Authentication Pipeline

The biometric verification workflow is based on facial embeddings.

```text
Input Image
     |
     v
Face Detection
     |
     v
Face Crop / Preprocessing
     |
     v
Face Embedding Generation
     |
     v
Embedding Comparison
     |
     v
Identity Verification
     |
     v
Authenticated Voter
     |
     v
Voting Workflow
```

### Embedding Generation

The project's face-processing workflow uses a pre-existing deep-learning face-recognition model to generate numerical facial representations, or **embeddings**.

These embeddings can then be used for identity comparison during voter verification.

The project should therefore be understood as an **AI application integrating an existing face-recognition model**, rather than a project that claims to have trained the underlying recognition model from scratch.

---

## 🛠️ Technology Stack

| Category             | Technology                |
| -------------------- | ------------------------- |
| Programming Language | Python                    |
| Backend Framework    | Flask                     |
| Machine Learning     | TensorFlow                |
| Face Recognition     | FaceNet / Face Embeddings |
| Face Detection       | MTCNN                     |
| Image Processing     | OpenCV, Pillow            |
| Numerical Computing  | NumPy                     |
| Scientific Computing | SciPy                     |
| Authentication       | Firebase Authentication   |
| Database             | Cloud Firestore           |
| Storage              | Firebase Storage          |
| Web Server           | Gunicorn                  |
| Containerization     | Docker                    |
| Frontend             | HTML / Jinja Templates    |
| Data / Configuration | JSON                      |

---

## 📂 Project Structure

```text
yesvote1/
│
├── models/
│   └── ...
│
├── static/
│   └── ...
│
├── templates/
│   └── ...
│
├── utils/
│   └── ...
│
├── app.py
├── auth.py
├── admin_routes.py
├── superadmin_routes.py
├── face_embedder.py
├── register_voter.py
├── verify_voter.py
├── firebase_config.py
│
├── firestore.rules
├── storage.rules
├── requirements.txt
├── Dockerfile
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

Make sure the following are installed:

* Python 3.x
* pip
* Docker *(optional, for containerized execution)*
* A configured Firebase project

---

### Installation

Clone the repository:

```bash
git clone https://github.com/b-swaraj007/yesvote1.git
```

Navigate to the project:

```bash
cd yesvote1
```

Install Python dependencies:

```bash
pip install -r requirements.txt
```

---

## ▶️ Running the Application

The Flask application can be started using the project's main application entry point:

```bash
python app.py
```

For production-style serving with Gunicorn:

```bash
gunicorn app:app
```

The exact command may depend on the configured Flask application object in your local environment.

---

## 🐳 Docker

Build the Docker image:

```bash
docker build -t b-swaraj007/yesvote1 .
```

Run the container:

```bash
docker run -it b-swaraj007/yesvote1
```

Docker provides a consistent environment for running the Flask application and its dependencies.

---

## 🔐 Security

Security is an important part of the project's design.

The application includes:

* Firebase authentication
* Role-based access workflows
* Session-controlled application access
* Firestore security rules
* Firebase Storage rules
* Biometric identity verification
* Separate voter and administrative workflows

### Important

This project is an **academic / prototype e-voting system** and should not be considered suitable for real governmental or public elections without extensive independent security auditing.

A production election system would require additional measures such as:

* Formal threat modeling
* Independent security audits
* Cryptographic verification
* Strong auditability and tamper evidence
* Liveness / anti-spoofing mechanisms
* Privacy and data-protection controls
* Accessibility and operational testing
* Comprehensive automated testing

---



## ⚠️ Limitations

* Facial recognition performance can be affected by lighting, camera quality, pose, and image conditions.
* Biometric verification requires appropriate threshold selection and evaluation.
* The current system does not establish production-grade election security.
* A real-world deployment would require stronger anti-spoofing and liveness detection.
* Firebase and other external services introduce infrastructure and availability dependencies.
* The underlying face-recognition model is integrated into the application rather than trained from scratch as part of this project.

---

## 🔮 Future Improvements

* Implement and evaluate facial liveness detection.
* Add systematic biometric verification benchmarks.
* Improve robustness across varying image conditions.
* Add comprehensive unit and integration tests.
* Strengthen audit logging and tamper-evidence mechanisms.
* Improve privacy-preserving handling of biometric data.
* Add CI/CD automation.
* Improve deployment documentation and secret management.
* Conduct formal security and threat-model analysis.

---

## 👨‍💻 Author

**Swaraj Bhosale**

GitHub: [@b-swaraj007](https://github.com/b-swaraj007)

---
