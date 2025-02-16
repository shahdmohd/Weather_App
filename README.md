# 🌤 Weather App (Dockerized & Automated with Jenkins)

This is a simple *Flask-based weather application, containerized using **Docker* and deployed using *Jenkins*. The app fetches weather data and displays it in a user-friendly UI.

## 🚀 Features
- Displays real-time weather information.
- Built with *Flask (Python)*.
- *Dockerized* for easy deployment.
- *Automated Deployment* using *Jenkins Pipeline*.
- Runs on *two CentOS machines* using *Ansible*.
- Exposed on *port 5000*.

## 📸 Screenshots
| Docker Status | | Jenkins Pipeline Success | Browser Access 1 | Browser Access 2 |
|--------------|-------------------------|-----------------|-----------------|
| ![Docker Containers](screenshots/docker-containers.png) | | ![Jenkins Success](screenshots/pipeline.png) | ![Website 1](screenshots/1st-browser-access.png) | ![Website 2](screenshots/2nd-browser-access.png) |

---

## 🛠 Setup & Installation

### *1️⃣ Prerequisites*
Ensure you have the following installed:
- *Jenkins* (with Docker & Ansible integration)
- Docker  
- Python (if running locally)  
- Git (optional)

### *2️⃣ Clone the Repository*
```sh
git clone https://github.com/shahdmohd/weather-app.git
cd weather-app
