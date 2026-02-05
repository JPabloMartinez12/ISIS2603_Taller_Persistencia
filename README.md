# Taller Persistencia

## Enlaces de interés

- [BookstoreBack](https://github.com/Uniandes-isis2603/bookstore-back) -> Repositorio de referencia para el Back

1. Diseño de Relaciones: ¿En cuál de las entidades (Proyecto o Tarea) quedó la columna de la llave foránea (project_id) en la base de datos? Explica por qué esto es necesario.
- La columna de la llave foránea project_id quedó ubicada en la entidad Tarea, ya que la relación es de Uno a Muchos, donde un Proyecto puede tener muchas Tareas, pero cada Tarea pertenece a un único Proyecto. En las relaciones 1:N la clave foranea se almacena del lado de muchos (N).

2. Integridad de Datos: Describe qué configuración específica utilizaste para que al borrar un Proyecto desaparezcan sus Tareas. ¿Cuál es la diferencia conceptual entre borrar la tarea de la lista del proyecto vs borrar el proyecto entero?
- Para asegurar que al borrar un Proyecto se eliminen automáticamente sus Tareas asociadas, se configura la relación con cascade = CascadeType.ALL y orphanRemoval = true en la entidad Proyecto. Eliminar el proyecyo implica que se borren las tareas asociadas ya que no tiene sentido que existan sin proyecyo asociado.

3. Consultas: Explica cómo funciona "por debajo" el método de búsqueda por estado. Si tuvieras que escribir el SQL de esa consulta manualmente, ¿cómo sería aproximadamente (SELECT ...)?
- El método de búsqueda por estado funciona mediante Query Methods de Spring Data JPA, donde el framework interpreta el nombre del método (findByEstado) y genera automáticamente la consulta correspondiente en tiempo de ejecución.
En SQL debería hacerse un SELECT de atributos FROM alguna tabla WHERE (condición de busqueda)

