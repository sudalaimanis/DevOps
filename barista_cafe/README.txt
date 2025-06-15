Bristacafe Web Server Docker Image
==================================

This project provides a Dockerized setup for the Bristacafe website using Apache2 on Ubuntu.
It automatically installs necessary packages, extracts the project files, and runs an Apache web server to serve the content.

--------------------------------------------------
Docker Image Details
--------------------------------------------------
- Base Image: ubuntu:latest
- Web Server: Apache2
- App Source: baristacafe.tar.gz (added to /var/www/html)
- Exposed Port: 80
- Volume: /var/log/apache2 for Apache logs
- Maintainer: Sudalaimani

--------------------------------------------------
Project Structure
--------------------------------------------------
.
├── Dockerfile
└── baristacafe.tar.gz

Ensure baristacafe.tar.gz is present in the build context. It should contain the web files for the Bristacafe project.

--------------------------------------------------
How to Build
--------------------------------------------------
docker build -t bristacafe:latest .

--------------------------------------------------
How to Run
--------------------------------------------------
docker run -d -p 8080:80 --name bristacafe_container bristacafe:latest

Then open your browser and go to: http://localhost:8080

--------------------------------------------------
Volumes
--------------------------------------------------
Logs from Apache are stored in a volume at:

/var/log/apache2

To map it to a local directory:

docker run -d -p 8080:80 -v $(pwd)/apache_logs:/var/log/apache2 --name bristacafe_container bristacafe:latest

--------------------------------------------------
Environment Variables
--------------------------------------------------
- DEBIAN_FRONTEND=noninteractive : Used to suppress interactive prompts during package installation.

--------------------------------------------------
Author
--------------------------------------------------
Name: Sudalaimani

--------------------------------------------------
License
--------------------------------------------------
This project is licensed for educational and demonstration purposes. You may modify and use it as needed.
