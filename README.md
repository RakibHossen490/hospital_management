
# 🏥 Hospital Management System

<div align="center">

![Developer](https://img.shields.io/badge/Developed%20By-MD%20Rakib%20Hossen%20Howladar-blue?style=flat-square)
![Django](https://img.shields.io/badge/Django-3.0.5-darkgreen?style=flat-square)
![Python](https://img.shields.io/badge/Python-3.7-blue?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active-success?style=flat-square)

A comprehensive Django-based Hospital Management System for managing doctors, patients, appointments, and billing operations.

</div>

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Technology Stack](#technology-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Screenshots](#screenshots)
- [Database Models](#database-models)
- [API Endpoints](#api-endpoints)
- [Known Limitations](#known-limitations)
- [Contributing](#contributing)
- [Disclaimer](#disclaimer)
- [Support](#support)

---

## 🎯 Overview

The Hospital Management System is a web-based application designed to streamline hospital operations. It provides separate modules for administrators, doctors, and patients, enabling efficient management of healthcare services including appointments, patient admissions, discharge procedures, and billing.

This system is built with Django 3.0.5 and uses SQLite for data persistence, making it lightweight and easy to deploy for demonstration and educational purposes.

---

## ✨ Features

### 👨‍💼 Admin Dashboard
- **User Management**: Register, approve, and manage doctors and patients
- **Doctor Management**: 
  - Register and approve doctors applying for positions
  - View doctor specializations and availability
  - Manage doctor incentives and performance metrics
- **Patient Management**: 
  - Admit and manage patient records
  - Assign doctors to patients
  - Discharge patients with detailed reports
- **Appointment Management**: 
  - View and approve/reject patient appointment requests
  - Generate appointment schedules
- **Billing & Invoice Generation**: 
  - Generate detailed invoices with itemized charges
  - Export invoices to PDF format
  - Track room charges, medicine costs, and doctor fees

### 👨‍⚕️ Doctor Portal
- **Application Process**: Apply for positions in hospitals
- **Patient Management**: 
  - View assigned patients with detailed information
  - Access patient symptoms and medical history
- **Appointment Management**: 
  - View scheduled appointments
  - Delete appointments after completion
  - Track consultation status
- **Discharge Management**: 
  - View list of discharged patients
  - Access discharge summaries

### 👤 Patient Portal
- **Account Management**: Create and manage personal accounts
- **Doctor Directory**: 
  - View available doctors by specialization
  - Access doctor contact information
- **Appointment Booking**: 
  - Request appointments with preferred doctors
  - Track appointment approval status
- **Medical Records**: 
  - View assigned doctor details
  - Download invoices and medical summaries

---

## 📁 Project Structure

```
hospitalmanagement-master/
├── hospital/                          # Main Django application
│   ├── models.py                     # Database models (Doctor, Patient, Appointment, etc.)
│   ├── views.py                      # View logic and routing
│   ├── forms.py                      # Django forms for user input
│   ├── admin.py                      # Django admin configuration
│   ├── apps.py                       # App configuration
│   ├── migrations/                   # Database migrations
│   └── __init__.py
├── hospitalmanagement/                # Project configuration
│   ├── settings.py                   # Django settings
│   ├── urls.py                       # URL routing
│   ├── wsgi.py                       # WSGI configuration
│   ├── asgi.py                       # ASGI configuration
│   └── __init__.py
├── templates/
│   └── hospital/                      # HTML templates
│       ├── index.html                # Home page
│       ├── admin*.html               # Admin templates
│       ├── doctor*.html              # Doctor templates
│       └── patient*.html             # Patient templates
├── static/
│   ├── style.css                     # Stylesheet
│   ├── images/                       # Static images
│   ├── profile_pic/                  # User profile pictures
│   └── screenshots/                  # Application screenshots
├── media/                            # Uploaded media files
├── manage.py                         # Django management script
├── db.sqlite3                        # SQLite database
├── requirement.txt                   # Python dependencies
└── README.md                         # This file
```

---

## 🛠 Technology Stack

| Component | Technology | Version |
|-----------|-----------|---------|
| Framework | Django | 3.0.5 |
| Language | Python | 3.7+ |
| Database | SQLite | 3 |
| Frontend | HTML5, CSS3 | - |
| PDF Generation | xhtml2pdf | Latest |
| UI Components | Django Widget Tweaks | 1.4.8 |
| Database Adapter | sqlparse | 0.3.1 |

---

## 📋 Prerequisites

Before you begin, ensure you have the following installed on your system:

- **Python 3.7+** - [Download Python](https://www.python.org/downloads/)
- **pip** - Python package manager (included with Python)
- **Git** (optional) - For version control
- **Virtual Environment** - Recommended for project isolation

---

## 🚀 Installation

### Step 1: Clone or Download the Repository

```bash
# Using Git
git clone https://github.com/sumitkumar1503/hospitalmanagement.git
cd hospitalmanagement-master

# OR manually download and extract the ZIP file
```

### Step 2: Create and Activate Virtual Environment

**Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

**macOS/Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirement.txt
```

This will install:
- Django 3.0.5
- django-widget-tweaks 1.4.8
- xhtml2pdf (for PDF generation)
- sqlparse 0.3.1

### Step 4: Apply Database Migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

### Step 5: Run the Development Server

```bash
python manage.py runserver
```

The application will be available at: **http://127.0.0.1:8000/**

---

## ⚙️ Configuration

### Email Configuration (For Contact Us Feature)

To enable the "Contact Us" email functionality:

1. Open `hospitalmanagement/settings.py`
2. Locate the email configuration section and update:

```python
# Email Configuration
EMAIL_HOST = 'smtp.gmail.com'
EMAIL_HOST_USER = 'your_email@gmail.com'
EMAIL_HOST_PASSWORD = 'your_email_password'
EMAIL_RECEIVING_USER = 'your_email@gmail.com'
EMAIL_PORT = 587
EMAIL_USE_TLS = True
```

3. **For Gmail Users**:
   - Generate an App Password: [Google App Passwords](https://myaccount.google.com/apppasswords)
   - Use the App Password in `EMAIL_HOST_PASSWORD`

4. **Alternative**: Enable "Less Secure Apps": [Google Less Secure Apps](https://myaccount.google.com/lesssecureapps)

### Customization

- **Update APP Name**: Modify app name in `hospitalmanagement/settings.py`
- **Modify Doctor Specializations**: Edit the `departments` list in `hospital/models.py`
- **Change Database**: Update `DATABASES` configuration in `settings.py`

---

## 📖 Usage

### First-Time Setup

1. **Create Default Admin User** (optional):
   ```bash
   python manage.py createsuperuser
   ```

2. **Access Django Admin Panel**:
   - Navigate to: http://127.0.0.1:8000/admin
   - Login with superuser credentials

### Role-Based Access

#### For Admins:
1. Go to http://127.0.0.1:8000/
2. Click "Admin Login"
3. Create account (immediate access)
4. Access dashboard to manage doctors, patients, and appointments

#### For Doctors:
1. Go to http://127.0.0.1:8000/
2. Click "Doctor Login"
3. Apply for a position
4. Wait for admin approval
5. Once approved, login to access patient information and appointments

#### For Patients:
1. Go to http://127.0.0.1:8000/
2. Click "Patient Login"
3. Create an account
4. Wait for admin approval
5. Once approved, book appointments and manage medical records

---

## 📸 Screenshots

### Homepage
![Homepage](https://github.com/RakibHossen490/hospitalmanagement/blob/master/static/screenshots/homepage.png?raw=true)

### Admin Dashboard
![Admin Dashboard](https://github.com/RakibHossen490/hospitalmanagement/blob/master/static/screenshots/Admin_Dashboard_main.png?raw=true)

### Invoice Generation
![Doctor Dashboard](https://github.com/RakibHossen490/hospitalmanagement/blob/master/static/screenshots/Doctor_Dashboard.png?raw=true)

### Doctor Management
![Patient Dashboard](https://github.com/RakibHossen490/hospitalmanagement/blob/master/static/screenshots/Patient_Dashboard.png?raw=true)

### Doctor Management
![Patient Dashboard](https://github.com/RakibHossen490/hospitalmanagement/blob/master/static/screenshots/Doctor_Profile.png?raw=true)

---

## 🗄 Database Models

### Doctor Model
```python
- user: OneToOneField (User)
- profile_pic: ImageField
- address: CharField
- mobile: CharField
- department: CharField (choices)
- status: BooleanField (approval status)
```

### Patient Model
```python
- user: OneToOneField (User)
- profile_pic: ImageField
- address: CharField
- mobile: CharField
- symptoms: CharField
- assignedDoctorId: PositiveIntegerField
- admitDate: DateField
- status: BooleanField (approval status)
```

### Admin Model
```python
- user: OneToOneField (User)
- profile_pic: ImageField
- mobile: CharField
- status: BooleanField
```

### Appointment Model
```python
- patientId: PositiveIntegerField
- doctorId: PositiveIntegerField
- patientName: CharField
- doctorName: CharField
- appointmentDate: DateField
- description: TextField
- status: BooleanField
```

### PatientDischargeDetails Model
```python
- patientId: PositiveIntegerField
- patientName: CharField
- assignedDoctorName: CharField
- address: CharField
- mobile: CharField
- symptoms: CharField
- admitDate: DateField
- releaseDate: DateField
- daySpent: PositiveIntegerField
- roomCharge: PositiveIntegerField
- medicineCost: PositiveIntegerField
- doctorFee: PositiveIntegerField
- OtherCharge: PositiveIntegerField
- total: PositiveIntegerField
```

### Doctor Specializations
- Cardiologist
- Dermatologists
- Emergency Medicine Specialists
- Allergists/Immunologists
- Anesthesiologists
- Colon and Rectal Surgeons

---

## 🔗 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/` | GET | Homepage |
| `/adminclick` | GET | Admin login/signup |
| `/doctorclick` | GET | Doctor login/signup |
| `/patientclick` | GET | Patient login/signup |
| `/admin-signup` | POST | Admin signup |
| `/admin-login` | POST | Admin login |
| `/afterlogin` | GET | Dashboard routing |

---

## ⚠️ Known Limitations

1. **Open Admin Registration**: Any user can create an admin account without approval. Consider implementing:
   - Admin invitation system
   - Superuser creation through Django shell
   - Email verification

2. **Doctor Requirement**: At least one doctor must exist before admitting patients

3. **Password Management**: 
   - Users must update passwords on profile update pages
   - No password reset functionality currently available

4. **Security Concerns**:
   - `DEBUG = True` in production (should be `False`)
   - `ALLOWED_HOSTS = []` should be configured for production
   - No HTTPS enforcement
   - SQL injection protection should be verified

5. **Scalability**: 
   - SQLite not suitable for production
   - No caching mechanism implemented
   - Limited concurrent user support

---

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## ⚖️ Disclaimer

**Important**: This project is developed for **demonstration and educational purposes only**. 

⚠️ **DO NOT USE IN PRODUCTION ENVIRONMENTS** without:
- Comprehensive security audit
- HIPAA compliance implementation (if applicable)
- Database migration to production-grade system
- Comprehensive testing and validation
- Professional deployment and maintenance

This system is not suitable for handling real patient medical data without significant enhancements and compliance measures.

---

## 📞 Support & Contact

### Project Author
- **Name**: MD Rakib Hossen Howladar

### Get Help
- Report Issues: [GitHub Issues](https://github.com/RakibHossen490)
- Contact: [Facebook](https://www.facebook.com/hm.rakibul404)

### Resources
- Django Documentation: [docs.djangoproject.com](https://docs.djangoproject.com)
- Python Documentation: [python.org](https://www.python.org)
- xhtml2pdf Documentation: [xhtml2pdf.readthedocs.io](https://xhtml2pdf.readthedocs.io)

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🎓 Educational Value

This project serves as an excellent learning resource for:
- Django web framework fundamentals
- Database modeling and relationships
- User authentication and authorization
- Form handling and validation
- PDF generation with Python
- Role-based access control
- MVC architecture implementation

---

**Last Updated**: April 2026  
**Version**: 1.0.0  
**Status**: Demo Release
