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

## Utilidades dentro de la interfaz

### Creación de variables
Podemos crear variables dentro de Airflow, y luego usarlas dentro de nuestro código, por ejemplo el nombre del environment.
Se pueden crear variables tipo Json y luego cargarlas en el código.
Para crearlas, dentro de la interfaz gráfica, debemos crearla en la pestaña Admin/Variables.


Luego para usarla en el código debemos usar el siguiente bloque de ejemplo:

```python
from airflow.models import Variable

var = Variable.get("<nombre_de_variable_creada>")
var_json = Variable.get("<nombre_variable_json>", deserialize_json=True)
```

### Creación de conexiones
Desde la interfaz, se pueden definir las diferentes conexiones que necesitemos, por ejemplo a una base de datos o a un bucket storage. 
Para ello se debe crear dentro de Admin/Connection y en el connection type definir la conexión necesaria. Esta nos pedira la información necesaria para conectarnos a donde sea necesario.

Para utilizarla en el código, dependiendo del operador, nos pedira un connection_id (conn_id), en el cual le especificaremos el nombre de la conexión creada.



