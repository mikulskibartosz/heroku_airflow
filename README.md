# Run Apache Airflow on Heroku
[Apache Airflow](https://airflow.apache.org/) can be used to create, schedule, and monitor workflows.  It is commonly used to define ETL processes.  An excellent example of an ETL workflow can be found [here](https://gtoonstra.github.io/etl-with-airflow/etlexample.html)

### Heroku Button deployment
Apache Airflow can be quickly and easily deployed to your own Heroku app by using this Heroku Button:
[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

You will be prompted for a new Fernet key, which can be generated thusly:

    dd if=/dev/urandom bs=32 count=1 2>/dev/null | openssl base64

After deployment a login user will need to be created.  This can be done using the `create_user` command through Heroku bash ([documentation](https://airflow.apache.org/cli.html#create_user))
    
    heroku run bash
    airflow users create     --username admin     --firstname Admin     --lastname Admin     --role Admin     --email admin@admin.org
