# Setting Up a DBT Project with Dagster on Windows

This guide walks you through setting up a DBT project in conjunction with Dagster on a Windows machine. Follow the steps below to ensure a smooth setup and execution process.

## Prerequisites

- Python version less than 3.12 (e.g., 3.11.5)
- Windows operating system
- Command-line interface (PowerShell or VSCode Terminal)

## Setting Up the Python Environment

1. **Install `virtualenv`**:
    ```sh
    pip install virtualenv
    ```

2. **Create a virtual environment**:
    ```sh
    virtualenv venv
    ```

3. **Activate the virtual environment**:
    ```sh
    venv\Scripts\activate
    ```

4. **Install the required dependencies**:
    Make sure you have a `requirements.txt` file with the necessary packages listed. Then run:
    ```sh
    pip install -r requirements.txt
    ```

## Setting Up DBT

1. **Initialize the DBT profiles folder**:
    Open a command prompt or PowerShell and run:
    ```sh
    mkdir %userprofile%\.dbt
    ```

2. **Create a DBT project**:
    Run the following command to initialize a new DBT project:
    ```sh
    dbt init dbtlearn
    ```

3. **Configure the DBT settings**:
    Navigate to the `dbtlearn` folder and configure the `profiles.yml` file according to your database connection settings.

4. **Check the connection**:
    To ensure that your DBT setup is correctly configured, run:
    ```sh
    dbt debug
    ```

## Running DBT Models

1. **Run DBT models**:
    To run all models, use:
    ```sh
    dbt run
    ```

2. **Full-refresh run**:
    To perform a full-refresh, use:
    ```sh
    dbt run --full-refresh
    ```

## Setting Up Dagster with DBT

1. **Navigate to the project directory**:
    ```sh
    cd dbt_dagster_project
    ```

2. **Set the environment variable**:
    In PowerShell, set the environment variable required for Dagster to parse the DBT project on load:
    ```sh
    $env:DAGSTER_DBT_PARSE_PROJECT_ON_LOAD = 1
    ```

3. **Start Dagster**:
    To start the Dagster development server, run:
    ```sh
    dagster dev
    ```

## Summary

This guide covered the following steps:
- Setting up a virtual environment for your Python project.
- Installing the necessary dependencies.
- Initializing and configuring a DBT project.
- Running DBT models and performing a full-refresh.
- Setting up Dagster to work with your DBT project and starting the Dagster development server.

By following these steps, you should be able to set up and run a DBT project integrated with Dagster on a Windows machine.

