# Jenkins CI/CD Pipeline Of Java Unipod Booking System

This repository demonstrates a **CI/CD pipeline** using **Jenkins** to automate the build and test process for the **Unipod Booking System**. The original project was used for testing out the integration of **Jenkins** with **GitHub** and **Maven**, specifically as a **lab rat repo** for learning and experimenting with CI/CD processes.

> **Note:** The **Unipod Booking System repository** is private, and this project serves as a demonstration of the **Jenkins pipeline configuration** that was used to automate its build, test, and deploy processes.

## Key Features:

- **Source Code Management (SCM):** The pipeline pulls code from the private GitHub repository (not included here).
- **Automated Builds:** Maven is used to clean and package the Java-based application into a JAR file.
- **Test Execution:** JUnit test results are automatically generated and published as part of the build process.
- **Build Artifacts:** The built JAR files are archived after each successful build.
- **Failure Notifications:** If the build fails, an email notification is sent to alert the team.

## Jenkins Pipeline Configuration

The repository contains a **Jenkinsfile** with the following pipeline steps:

1. **Code Checkout:** Pulls the latest code from the GitHub repository.
2. **Maven Build:** Executes `mvn clean package` to build the application.
3. **JUnit Test Reporting:** Publishes test results from the `target/surefire-reports` directory.
4. **Artifact Archiving:** Archives the JAR files produced by the Maven build.
5. **Email Notification:** Sends an email to notify about build failures.

## How to Use This Repository

This project is designed to showcase how you can set up a Jenkins pipeline for automating the build, test, and deploy process. If you'd like to access the full documentation or have questions, please feel free to reach out to me at **[qthmichaels@gmail.com](mailto:qthmichaels@gmail.com)**.

### Steps to Set Up Your Own Pipeline:

1. **Fork this repository** to your GitHub account.
2. **Create a Jenkins pipeline job** and point it to your forked repository.
3. Set up **Maven 3.9.9** on your Jenkins instance and configure the environment.
4. Run the pipeline to automate your build, test, and deployment process.

## Prerequisites

- **Jenkins:** Set up Jenkins with necessary plugins (Git, Maven Integration, Email Extension).
- **Maven 3.9.9**: Configure Maven on Jenkins.
- **GitHub Repository:** Ensure the GitHub repository contains the source code for your application (private repository).

## Contact

For detailed documentation, issues, or questions, please reach out to me at **[qthmichaels@gmail.com](mailto:qthmichaels@gmail.com)**.

---

### License

This project is open-source 
