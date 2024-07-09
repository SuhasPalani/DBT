# DBT with real world project


pip install virtualenv
virtualenv venv
venv\Scripts\activate

pip install -r requirements.txt

works well for python version less than 3.12 (mine is 3.11.5)

dbt setup

Initialize the dbt profiles folder on Windows:

mkdir %userprofile%\.dbt
Create a dbt project (all platforms):

dbt init dbtlearn
configure the settings
then go inside the folder dbtlearn and check for the connection success, dbt debug


to run models: dbt run

Making a full-refresh: dbt run --full-refresh


On Windows - PowerShell (Like the VSCode Terminal Window)

cd dbt_dagster_project
$env:DAGSTER_DBT_PARSE_PROJECT_ON_LOAD = 1
dagster dev