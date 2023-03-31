## Ramesses II (log)
[ramessesII](https://github.com/elwood777/ramessesII)
**REACTJS Simple Utility App**
A simple applicaion to showcase a solid understanding ReactJS.   

**Objective**   
Create a dynamic interface that allows users to add, edit, and delete items from the list. 

## Getting Started
Create a new React component called "ramessesII" (To Do List) 
```
npx create-react-app ramessesii
```  
  
In this component, we're using the "useState" hook to manage the list of todos. We're also using the "map" method to render the list of todos, and the "filter" method to remove a todo from the list when the "Delete" button is clicked.
```jsx  
import React, { useState } from 'react';

function TodoList() {
  const [todos, setTodos] = useState([]);

  const handleAddTodo = (event) => {
    event.preventDefault();
    const newTodo = event.target.elements.todo.value;
    setTodos([...todos, newTodo]);
  };

  const handleDeleteTodo = (index) => {
    setTodos(todos.filter((todo, i) => i !== index));
  };

  return (
    <div>
      <h1>Todo List</h1>
      <form onSubmit={handleAddTodo}>
        <input type="text" name="todo" />
        <button type="submit">Add</button>
      </form>
      <ul>
        {todos.map((todo, index) => (
          <li key={index}>
            {todo}
            <button onClick={() => handleDeleteTodo(index)}>Delete</button>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default TodoList;

```  


```jsx  
import React from 'react';
import TodoList from './TodoList';

function App() {
  return (
    <div>
      <TodoList />
    </div>
  );
}

export default App;

```  





## Other Commands
Starts the development server.
```  
$ npm start
```  

Bundles the app into static files for production.
```  
$ npm run build
``` 

Starts the test runner.
```  
$ npm test
``` 

Removes this tool and copies build dependencies, configuration files and scripts into the app directory.
```  
$ npm run eject
``` 