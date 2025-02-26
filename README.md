# Weather Data ETL Pipeline with Airflow

A sample ETL pipeline that extracts weather data from the OpenWeatherMap API, transforms it using Python, and loads it into a PostgreSQL database running on Docker. Finally, the data is deployed or hosted in an Amazon RDS instance for further analysis and usage.

## Table of Contents
- [Overview](#overview)
- [Architecture](#architecture)
- [Features](#features)
- [Technologies](#technologies)
- [Project Setup](#project-setup)
- [Usage](#usage)
- [Troubleshooting](#troubleshooting)
- [License](#license)
- [Contributing](#contributing)

---

## Overview
This project demonstrates a simple data engineering workflow using Apache Airflow, Docker, and PostgreSQL. The pipeline retrieves data from an external weather API, applies necessary transformations, and then stores the data in a PostgreSQL database containerized with Docker. Finally, you can replicate or host the database on Amazon RDS for production use.

---

## Architecture

- **Open API Weather Data**  
  Source of weather data (e.g., OpenWeatherMap API).

- **DAG Workflows (Apache Airflow)**
  - **Extract**: Periodically fetch data from the weather API.
  - **Transform**: Process and clean the data using Python.
  - **Load**: Insert the transformed data into PostgreSQL.

- **PostgreSQL Database**
  - Containerized using Docker.
  - Stores processed weather data.

- **Amazon RDS**
  - Optionally, replicate or migrate your local PostgreSQL to Amazon RDS for production or scaling.

---

## Features
- **Scheduled Data Extraction**: Automatic scheduling of API calls to fetch the latest weather data.
- **Data Transformation**: Cleans, structures, and formats raw data for analysis.
- **Containerized Environment**: Docker-based deployment for consistent and portable environments.
- **Easy Scalability**: Move from local PostgreSQL to Amazon RDS with minimal changes.

---

## Technologies
- **[Apache Airflow](https://airflow.apache.org/docs/)**: For orchestrating and scheduling ETL tasks.
- **[Docker](https://docs.docker.com/)**: For containerizing the application and database.
- **Python**: For data transformation and script-based automation.
- **[PostgreSQL](https://www.postgresql.org/)**: Database for storing processed data.
- **[Amazon RDS](https://aws.amazon.com/rds/)**: Cloud-based database hosting (optional for production).

---

## Project Setup

### Clone the Repository
```bash
git clone https://github.com/YourUsername/your-weather-etl.git
cd your-weather-etl


A sample ETL pipeline that extracts weather data from the OpenWeatherMap API, transforms it using Python, and loads it into a PostgreSQL database running on Docker. Finally, the data is deployed or hosted in an Amazon RDS instance for further analysis and usage.



Overview
========

Welcome to Astronomer! This project was generated after you ran 'astro dev init' using the Astronomer CLI. This readme describes the contents of the project, as well as how to run Apache Airflow on your local machine.

Project Contents
================

Your Astro project contains the following files and folders:

- dags: This folder contains the Python files for your Airflow DAGs. By default, this directory includes one example DAG:
    - `example_astronauts`: This DAG shows a simple ETL pipeline example that queries the list of astronauts currently in space from the Open Notify API and prints a statement for each astronaut. The DAG uses the TaskFlow API to define tasks in Python, and dynamic task mapping to dynamically print a statement for each astronaut. For more on how this DAG works, see our [Getting started tutorial](https://www.astronomer.io/docs/learn/get-started-with-airflow).
- Dockerfile: This file contains a versioned Astro Runtime Docker image that provides a differentiated Airflow experience. If you want to execute other commands or overrides at runtime, specify them here.
- include: This folder contains any additional files that you want to include as part of your project. It is empty by default.
- packages.txt: Install OS-level packages needed for your project by adding them to this file. It is empty by default.
- requirements.txt: Install Python packages needed for your project by adding them to this file. It is empty by default.
- plugins: Add custom or community plugins for your project to this file. It is empty by default.
- airflow_settings.yaml: Use this local-only file to specify Airflow Connections, Variables, and Pools instead of entering them in the Airflow UI as you develop DAGs in this project.

Deploy Your Project Locally
===========================

1. Start Airflow on your local machine by running 'astro dev start'.

This command will spin up 4 Docker containers on your machine, each for a different Airflow component:

- Postgres: Airflow's Metadata Database
- Webserver: The Airflow component responsible for rendering the Airflow UI
- Scheduler: The Airflow component responsible for monitoring and triggering tasks
- Triggerer: The Airflow component responsible for triggering deferred tasks

2. Verify that all 4 Docker containers were created by running 'docker ps'.

Note: Running 'astro dev start' will start your project with the Airflow Webserver exposed at port 8080 and Postgres exposed at port 5432. If you already have either of those ports allocated, you can either [stop your existing Docker containers or change the port](https://www.astronomer.io/docs/astro/cli/troubleshoot-locally#ports-are-not-available-for-my-local-airflow-webserver).

3. Access the Airflow UI for your local Airflow project. To do so, go to http://localhost:8080/ and log in with 'admin' for both your Username and Password.

You should also be able to access your Postgres Database at 'localhost:5432/postgres'.

Deploy Your Project to Astronomer
=================================

If you have an Astronomer account, pushing code to a Deployment on Astronomer is simple. For deploying instructions, refer to Astronomer documentation: https://www.astronomer.io/docs/astro/deploy-code/

Contact
=======

The Astronomer CLI is maintained with love by the Astronomer team. To report a bug or suggest a change, reach out to our support.
