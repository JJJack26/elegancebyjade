# Elegance by Jade: Hair Product Purchasing

# Overview
This webapp was created for a school project for introduction into DevOps

# Features
1. Homepage displaying just four varieties of one of the products that elegancebyjade sells
2. Additional page to see more details of selected product..

# What's Needed?
1. Python 3.12 and Django installed
2. Docker installed
3. Git installed
4. Jenkins installed locally and Authenticated


# Steps to run Locally
1. Clone the Repository 
   - git clone https://github.com/JJJack26/elegancebyjade.git

2. Navigate to project folder
   - cd elegancebyjade

3. Install the python requirements
   - pip install -r requirements.txt
    
4. Run the django server
   - python manage.py runserver/ python3 manage.py runserver (for mac)

5. Access the Web Application:
   - Open your web browser and go to http://localhost:8000 or 127.0.0.1:8000
    

# Jenkins Pipeline
The Jenkins pipeline automates the build and deployment of the application

Pipeline Stages
- Checkout:Checks out the code from the Git repository.
- Build Docker Image: Builds the Docker image for the web application.
- Push Docker Image: Pushes the Docker image to the Docker registry.


# Contributors
- Jade Romain
- jaderomainjack26@gmail.com