<!-- hide -->
# Segunda parte de la TODO List, agregando fetch
<!-- endhide -->

Debes hacer este ejercicio después de la [aplicación de la TODO list con React](https://4geeks.com/es/interactive-coding-tutorial/todo-list-es) porque la primera parte es el boilerplate perfecto para comenzar a usar APIs.

Para esta segunda parte, sincronizaremos nuestra lista de tareas con una base de datos real, usando la siguiente [RESTful](https://4geeks.com/es/lesson/understanding-rest-apis-es) y API pública realizada para este ejercicio.

🔗 Clic aquí para acceder a la [documentación de la API del TODO-list](https://playground.4geeks.com/todo/docs).

👉 [Aqui hay un video explicando como usar el TODO-List API con Fetch](https://www.youtube.com/watch?v=s6_-c0LFDRo).

Todo este ejercicio se trata de la programación asíncrona porque las interacciones *desde* y *hacia* el servidor deben realizarse de forma asíncrona. De esa manera, el usuario no tiene que esperar a que llegue la información.

<onlyfor saas="false" withBanner="false">
      
## 🌱 Cómo comenzar este proyecto

No clones este repositorio porque vamos a usar una plantilla diferente.

Recomendamos abrir el `react boilerplate` usando un entorno de desarrollo como [Codespaces](https://4geeks.com/es/lesson/tutorial-de-github-codespaces) (recomendado) o [Gitpod](https://4geeks.com/es/lesson/como-utilizar-gitpod). Alternativamente, puedes clonarlo en tu computadora local usando el comando `git clone`.

Este es el repositorio que necesitas abrir o clonar:

```text
https://github.com/4GeeksAcademy/react-hello
```

**👉 Por favor sigue estos pasos sobre** [cómo comenzar un proyecto de programación](https://4geeks.com/es/lesson/como-comenzar-un-proyecto-de-codificacion).

> 💡 Importante: Recuerda guardar y subir tu código a GitHub creando un nuevo repositorio, actualizando el remoto (`git remote set-url origin <your new url>`) y subiendo el código a tu nuevo repositorio usando los comandos `add`, `commit` y `push` desde la terminal de git.

</onlyfor>

## 📝 Instrucciones :
Tu aplicación de TODO List debe mantenerse sincronizada con el backend cada vez que se agregue o elimine una tarea. Además, debe incluir un botón de limpieza que elimine toda la lista en el servidor y actualice el frontend con una lista vacía.

 ##👉 Momentos clave para la integración :
 
1. Cargar tareas al iniciar (useEffect)
   • Usa el método GET /users/{user_name} para obtener la lista y actualizar el estado.

2. Agregar una tarea
   • Usa POST /todos/{user_name} para añadir una nueva tarea.
   •Luego, usa GET para actualizar la lista.

3. Eliminar una tarea
   •Usa DELETE /todos/{todo_id} y luego GET para actualizar la lista.
   
4. Eliminar todas las tareas (Botón de limpieza)🅇
   •Usa DELETE en cada tarea o un endpoint para limpiar todo.
   •Luego, usa GET para reflejar los cambios en la interfaz.

 ## ☝️Asegúrate de crear un usuario antes de añadir tareas.

## 💡 Pista:

Utiliza el siguiente fetch call para crear una nueva tarea en el servidor. Recuerda crearte un usuario primero. 

```js
fetch('https://playground.4geeks.com/todo/todos/alesanchezr', {
      method: "POST",
      body: JSON.stringify(todo),
      headers: {
        "Content-Type": "application/json"
      }
    })
    .then(resp => {
        console.log(resp.ok); // Será true si la respuesta es exitosa
        console.log(resp.status); // El código de estado 201, 300, 400, etc.
        console.log(resp.text()); // Intentará devolver el resultado exacto como string
        return resp.json(); // Intentará parsear el resultado a JSON y retornará una promesa donde puedes usar .then para seguir con la lógica
    })
    .then(data => {
        // Aquí es donde debe comenzar tu código después de que finalice la búsqueda
        console.log(data); // Esto imprimirá en la consola el objeto exacto recibido del servidor
    })
    .catch(error => {
        // Manejo de errores
        console.log(error);
    });
```

Para cualquier otra solicitud, debes cambiar las variables en el fetch: La URL, el método y el payload.

Este y otros proyectos son usados para [aprender a programar](https://4geeksacademy.com/es/aprender-a-programar/aprender-a-programar-desde-cero) por parte de los alumnos de 4Geeks Academy [Coding Bootcamp](https://4geeksacademy.com/us/coding-bootcamp) realizado por [Alejandro Sánchez](https://twitter.com/alesanchezr) y muchos otros contribuyentes. Conoce más sobre nuestros [Cursos de Programación](https://4geeksacademy.com/es/curso-de-programacion-desde-cero?lang=es) para convertirte en [Full Stack Developer](https://4geeksacademy.com/es/coding-bootcamps/desarrollador-full-stack/?lang=es), o nuestro [Data Science Bootcamp](https://4geeksacademy.com/es/coding-bootcamps/curso-datascience-machine-learning).
