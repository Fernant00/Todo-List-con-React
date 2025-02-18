# Todo List con React
# Create and Implement code to add task.

```jsx
  function handleSubmit(e) {
    e.preventDefault(); // Previene el comportamiento por defecto del formulario

    // Obtiene el valor del campo de entrada para la nueva tarea
    let todo = document.getElementById('todoAdd').value;

    // Crea un nuevo objeto representando la tarea
    const newTodo = {
        id: new Date().getTime(), // Genera un id único basado en la fecha y hora actual
        text: todo.trim(), // Asigna el texto de la tarea, eliminando espacios en blanco al inicio y al final
        completed: false, // Inicializa la tarea como no completada
    };

    // Verifica si el texto de la tarea es válido (no está vacío)
    if (newTodo.text.length > 0) {
        // Crea una nueva matriz con todas las tareas existentes y agrega la nueva tarea al final
        setTodos([...todos].concat(newTodo));
    } else {
        // Si el texto de la tarea es vacío, muestra una alerta
        alert("Ingrese una tarea válida");
    }

    // Limpia el campo de entrada después de agregar la tarea
    document.getElementById('todoAdd').value = "";
}

```
# Exercise 2: Delete a completed task from the list.

```jsx
function deleteTodo(id) {
    // Crea una nueva matriz excluyendo la tarea con el ID dado
    let updatedTodos = [...todos].filter((todo) => todo.id !== id);
    
    // Actualiza el estado con la nueva matriz de tareas
    setTodos(updatedTodos);
}

```
# Exercise 3: Adding Checkbox and Toggle function.

```jsx
function toggleComplete(id) {
    // Crea una copia de la matriz 'todos' usando el operador spread
    let updatedTodos = [...todos].map((todo) => {
        // Comprueba si el id de la tarea actual coincide con el id proporcionado
        if (todo.id === id) {
            // Si coincide, cambia el estado de completitud de la tarea
            todo.completed = !todo.completed;
        }
        return todo; // Devuelve la tarea modificada o sin modificar
    });
    
    // Actualiza el estado con la nueva matriz 'updatedTodos'
    setTodos(updatedTodos);
}

```
# Exercise 4: Edit a added Todo task and submit it.

```jsx
function toggleComplete(id) {
    // Crea una copia de la matriz 'todos' usando el operador de propagación
    let updatedTodos = [...todos].map((todo) => {
        // Verifica si el ID de la tarea actual coincide con el ID proporcionado
        if (todo.id === id) {
            // Invierte el estado de completitud de la tarea
            todo.completed = !todo.completed;
        }
        return todo; // Devuelve la tarea modificada o sin modificar
    });
    
    // Actualiza el estado de las tareas con la nueva matriz 'updatedTodos'
    setTodos(updatedTodos);
}

```
# Exercise 5: Adding the useEffect hook.

```jsx
useEffect(() => {
    // Carga las tareas guardadas en el almacenamiento local cuando el componente se monta
    const json = localStorage.getItem("todos"); // Obtiene las tareas guardadas en formato JSON
    const loadedTodos = JSON.parse(json); // Parsea las tareas desde JSON a objetos JavaScript
    if (loadedTodos) {
        setTodos(loadedTodos); // Actualiza el estado con las tareas cargadas si existen
    }
}, []);
useEffect(() => {
    // Guarda las tareas en el almacenamiento local cada vez que la lista de tareas cambia
    if (todos.length > 0) {
        const json = JSON.stringify(todos); // Convierte las tareas a formato JSON
        localStorage.setItem("todos", json); // Guarda las tareas en el almacenamiento local
    }
}, [todos]);

```

# conclusiones

El codigo esta muy completo y no presenta fallas,explica de manera clara cada paso y procedimiento de como ir haciendo cada ejercicio, la manera en como esta desglozado cada parte del codigo la hace mas dinamica y facil de comprender, solo que no me gusto que no explicaran que hace algunos fracmentos del codigo ya que existen funciones o metodos que se usan a lo largo del codigo que no se cuenta con el conocimiento y resulta dificil de comprender. #   T o d o - L i s t - c o n - R e a c t  
 