# Fundamentos de Apache AirFlow


## Conceptos de Airflow

- **DAG**: Directed acyclic graph, flujo de trabajo, indica como se relacionan las tareas entre si y su orden de ejecución. Son direccionados ya que nos indican que tarea va luego de cual otra, y son aciclicos ya que esto generaria problemas a la hora de ejecutar los flujos.
- **Task**: componente interno de los DAGs, es como tal una tarea atómica que se va a realizar.
- **Operator**: unidad única de trabajo, describe que tipo de tarea se va a realizar.


## Componentes de Airflow

<img width="442" alt="Screenshot 2024-02-19 at 6 07 04 PM" src="https://github.com/Jusariasve/study_notes/assets/18059093/40696a84-0f9d-4741-ade2-db060bbda46c">

- **Scheduler**: Se encarga de controlar la ejecución de las tareas a través del tiempo.
- **DAG directory**: Almacena los ficheros python con la definicion de los DAGs, tareas, dependencias, etc.
- **Workers**: Son los ejecutores, que se encargan de iniciar las tareas y verificar su estado.
- **Metadata Database**: En esta se almacena la información de la ejecución de los DAGs.
- **Web Server**: Soporta la interfaz de usuario.
- **User Interface**: Interfaz de usuario para monitorear el funcionamiento de nuestros procesos.


