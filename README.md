# Lista-de-tareas
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Mi Lista de Tareas</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(to right, #74ebd5, #9face6);
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      height: 100vh;
    }

    h1 {
      margin-top: 40px;
      color: #fff;
    }

    .container {
      background-color: white;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
      width: 90%;
      max-width: 400px;
    }

    input[type="text"] {
      width: 70%;
      padding: 10px;
      margin-right: 10px;
      border: 1px solid #ddd;
      border-radius: 6px;
    }

    button {
      padding: 10px 15px;
      background-color: #5e60ce;
      color: white;
      border: none;
      border-radius: 6px;
      cursor: pointer;
    }

    button:hover {
      background-color: #4ea8de;
    }

    ul {
      list-style: none;
      padding: 0;
      margin-top: 20px;
    }

    li {
      background: #f1f1f1;
      padding: 10px;
      border-radius: 6px;
      margin-bottom: 10px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .delete {
      background: #ff4d4d;
      border: none;
      color: white;
      padding: 5px 8px;
      border-radius: 5px;
      cursor: pointer;
    }

    .delete:hover {
      background: #e60000;
    }
  </style>
</head>
<body>
  <h1>📝 Mi Lista de Tareas</h1>
  <div class="container">
    <input type="text" id="taskInput" placeholder="Escribe una tarea..." />
    <button onclick="addTask()">Agregar</button>
    <ul id="taskList"></ul>
  </div>

  <script>
    function addTask() {
      const input = document.getElementById("taskInput");
      const taskText = input.value.trim();

      if (taskText === "") return;

      const li = document.createElement("li");
      li.textContent = taskText;

      const deleteBtn = document.createElement("button");
      deleteBtn.textContent = "Eliminar";
      deleteBtn.className = "delete";
      deleteBtn.onclick = () => li.remove();

      li.appendChild(deleteBtn);
      document.getElementById("taskList").appendChild(li);

      input.value = "";
    }
  </script>
</body>
</html>

