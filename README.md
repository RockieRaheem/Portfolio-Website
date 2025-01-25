# Raheem Portfolio Website - Containerized with Docker and CI/CD Pipeline
This repository contains a portfolio website that is containerized using Docker. It also integrates a Continuous Integration/Continuous Deployment (CI/CD) pipeline with GitHub Actions to automate the deployment process.

# Project Overview
This project demonstrates the following:

Creating a simple portfolio website.
Containerizing the website using Docker.
Setting up a GitHub Actions CI/CD pipeline for automated build and deployment.
Prerequisites
Before running the application locally or contributing to this project, make sure you have the following installed:

# Docker: 
For containerizing the application.
# Git: 
To clone the repository and manage version control.
# GitHub Account: 
To clone and push changes to the repository.
# Optional: 
Kubernetes for orchestration if the application needs to be scaled.

# Steps to Run the Application Locally
Clone the repository:

bash
Copy
Edit
git clone https://github.com/RockieRaheem/Raheem-Portfolio-Website.git
cd Raheem-Portfolio-Website
Build the Docker image:

bash
Copy
Edit
docker build -t raheem-portfolio-website .
Run the Docker container:

bash
Copy
Edit
docker run -p 8080:8080 raheem-portfolio-website
View the application: Open a browser and go to http://localhost:8080 to view the portfolio website.

# Dockerization
In this project, the web application is containerized using Docker. The Dockerfile defines the containerization process. Here’s the content of the Dockerfile:

Dockerfile
Copy
Edit
# Use a base image
FROM node:14

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy the application source code into the container
COPY . .

# Expose the port the app runs on
EXPOSE 8080

# Command to run the application
CMD ["npm", "start"]
CI/CD Pipeline with GitHub Actions
The project uses GitHub Actions to set up a CI/CD pipeline, defined in the .github/workflows/ci-cd.yml file. The pipeline automates the following:

# Running tests (if any).
Building the Docker image.
Deploying the container (this can be to any cloud provider or server).

# Folder Structure
Here’s an overview of the folder structure:

graphql
Copy
Edit
Raheem-Portfolio-Website/
│
├── .git/                    # Git version control
├── .github/                 # GitHub Actions workflows
│   └── workflows/           # CI/CD workflow file
│       └── ci-cd.yml
├── images/                  # Folder for images 
├── src/                     # Source files
│   └── index.html           # The HTML for the portfolio website
│   └── script.js            # JavaScript for dynamic behavior
│   └── style.css            # CSS for styling
├── Dockerfile               # Dockerfile for containerizing the web app
├── README.md                # Project documentation
└── .gitignore               # Git ignore file

# Contributing
If you’d like to contribute to this project:

Fork the repository.
Create a new branch:
bash
Copy
Edit
git checkout -b feature-branch
Make your changes.
Commit your changes:
bash
Copy
Edit
git commit -am 'Add new feature'
Push to your branch:
bash
Copy
Edit
git push origin feature-branch
Create a pull request.