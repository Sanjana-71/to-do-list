<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <style>
       .body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .container {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 300px;
        }
        h1 {
            text-align: center;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px;
            border-bottom: 1px solid #ddd;
        }
        button {
            background-color: #ff6f61;
            border: none;
            color: white;
            padding: 5px 10px;
            cursor: pointer;
            border-radius: 5px;
        }
        button:hover {
            background-color: #e55b4e;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>To-Do List</h1>
        <input type="text" id="taskInput" placeholder="Add a new task" />
        <button onclick="addTask()">Add Task</button>
        <ul id="taskList"></ul>
    </div>
    <script>
        function addTask() {
            const taskInput = document.getElementById('taskInput');
            const taskValue = taskInput.value.trim();
            if (taskValue === '') {
                return;
            }
            const li = document.createElement('li');
            li.textContent = taskValue;
            const removeButton = document.createElement('button');
            removeButton.textContent = 'Remove';
            removeButton.onclick = function() {
                li.remove();
            };
            li.appendChild(removeButton);
            document.getElementById('taskList').appendChild(li);
            taskInput.value = '';
        }
    </script>
</body>
</html>
