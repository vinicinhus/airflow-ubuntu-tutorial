# Installing Apache Airflow on Ubuntu

This tutorial guides you through the process of installing Apache Airflow on Ubuntu 22.04.03 LTS.

## Requirements

- [Ubuntu 22.04.03 LTS](https://ubuntu.com/download)
- Python 3

## Installing Python and Required Packages

1. **Install Python3:**

    ```bash
    sudo apt install python3-pip
    ```
    This command installs Python3, which is required for Apache Airflow.

# 

2. **Install `virtualenv`:**

    ```bash
    sudo pip3 install virtualenv
    ```
    Virtualenv allows you to create isolated Python environments. It's a good practice to manage dependencies for different projects.

# 

3. **Create and activate a virtual environment:**

    ```bash
    virtualenv airflow_env
    source airflow_env/bin/activate
    ```
    These commands create a virtual environment named `airflow_env` and activate it. Activating the virtual environment ensures that the subsequent installations are isolated.

#

4. **Install Apache Airflow:**

    ```bash
    pip3 install apache-airflow[gcp,sentry,statsd]
    ```
    Installs Apache Airflow along with additional packages for Google Cloud Platform integration, error tracking with Sentry, and metrics tracking with StatsD.

---

## Configuring Apache Airflow

1. **Initialize the Airflow database:**

    ```bash
    airflow db init
    ```
    This command initializes the Airflow metadata database. The metadata database is used to store information about DAGs, tasks, and other Airflow-related metadata.

# 

2. **Create a 'dags' folder to store your DAGs:**

    ```bash
    mkdir dags
    ```
    The 'dags' folder is where you'll store your Directed Acyclic Graphs (DAGs), which represent the workflows in Airflow.

# 

3. **Create an admin account:**

    ```bash
    airflow users create --username admin --password admin --firstname admin --lastname admin --role Admin --email example@hotmail.com
    ```
    This command creates an admin user account with the specified credentials.

# 

4. **List all created accounts:**

    ```bash
    airflow users list
    ```
    Lists all user accounts created in the Airflow instance.

# 

5. **Start the Airflow scheduler:**

    ```bash
    airflow scheduler
    ```
    The scheduler orchestrates the execution of tasks in your DAGs.

# 

6. **Start the Airflow web server:**

    ```bash
    airflow webserver
    ```
    The web server provides the Airflow UI, accessible at [localhost:8080](http://localhost:8080).


# 
7. **Access Airflow at [localhost:8080](http://localhost:8080) and log in with the admin account.**

# 
Now you have Apache Airflow set up on your Ubuntu machine. Customize and create your DAGs in the 'dags' folder.
