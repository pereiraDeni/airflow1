

# Airflow cli

Inicializa o DB
~~~
airflow initdb
~~~

Start the webserver

```
airflow webserver --port 8080 
```

Start the scheduler

```
airflow scheduler
``` 

list dags

```
airflow dags list or list_dags
```

Print list of tasks of dag id

```
airflow list_tasks dag_id
```

print the hierarchy of task in the dag

```
airflow list_tasks dag_id --tree
```

Test your Tasks in your DAG
```
airflow test dag_id task_id execution_date
```

#Dag Scheduling
#backfilling and catchup

start date 
schedule interval

start_date + schedule_interval = elapsed = first effective trigger
execution date = start date