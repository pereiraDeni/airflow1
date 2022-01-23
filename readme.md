

### Airflow cli

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

### Dag Scheduling
#### backfilling and catchup

start date 
schedule interval

start_date + schedule_interval = elapsed = first effective trigger
execution date = start date

### Taskgroup

group tasks with the same context.

for exemple: if you want to create a pipeline with multiples task but to 3 context diferent, as bank, financcial and insurers. 

You can execute parallel pipeline at the same time in the same dag but in taskgroup diferent incapse with a for loop.


### xcom

share data in differents taks, but with small data.

Some operators such as BashOperator or SimpleHttpOperator have a parameter called 
xcom_push=False by default. If you set xcom_push=True the last output will be pushed to an 
XCOM for the BashOperator or if you use SimpleHttpOperator, the response of the HTTP request 
will also be pushed to an XCOM


### branchOperator + trigger role

BranchPythonOperator run a task depends the result of the function in pythoncallable operator.
trigger_role run the next task depend of last task result.

trigger_role can be:
all_success, all_failed, all_done, one_success, one_failed, none_failed, none_failed_or_skipped
