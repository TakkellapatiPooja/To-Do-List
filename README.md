# To-Do-List
This project is a responsive and visually appealing to-do list application developed using HTML, CSS, and JavaScript. It allows users to manage daily tasks efficiently with real-time updates and dynamic numbering.

project description:
A modern, interactive to-do list web application built using HTML, CSS, and vanilla JavaScript, focused on efficient task management and clean user experience. The application dynamically handles task creation, completion, deletion, and automatic re-indexing of tasks in real time, ensuring accurate numbering at all times.

The project emphasizes DOM manipulation, event-driven programming, and UI responsiveness without relying on external libraries, making it lightweight and performance-optimized.
Key Features:
1.Dynamic task creation and deletion
2.Automatic task renumbering after every operation
3.Real-time task status updates.
4.Smooth animations and visually appealing centered layout
5.Clean, maintainable, and beginner-friendly JavaScript code
Technologies Used
1.HTML5 for structure
2.CSS3 for styling and animations
3.JavaScript (ES6) for logic and DOM manipulation

code:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Smart To-Do List</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', sans-serif;
        }

        body {
            height: 100vh;
            background: linear-gradient(135deg, #1d2671, #c33764);
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .todo-container {
            width: 430px;
            padding: 30px;
            border-radius: 22px;
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(14px);
            box-shadow: 0 25px 50px rgba(0,0,0,0.35);
            color: #fff;
            text-align: center;
        }

        h1 {
            margin-bottom: 22px;
            font-size: 26px;
        }

        .input-box {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
        }

        input {
            flex: 1;
            padding: 12px;
            border-radius: 10px;
            border: none;
            outline: none;
        }

        button {
            padding: 12px 16px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            background: #00f2fe;
            color: #000;
            font-weight: bold;
            transition: 0.3s;
        }

        button:hover {
            transform: scale(1.05);
        }

        ul {
            list-style: none;
            max-height: 300px;
            overflow-y: auto;
        }

        li {
            background: rgba(255,255,255,0.2);
            padding: 14px;
            margin-bottom: 12px;
            border-radius: 14px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            animation: slideIn 0.4s ease;
        }

        li.completed {
            background: rgba(0, 255, 150, 0.35);
            text-decoration: line-through;
        }

        .task-info {
            display: flex;
            align-items: center;
            gap: 6px;
            text-align: left;
        }

        .task-number {
            font-weight: bold;
        }

        .status {
            font-size: 18px;
        }

        .actions button {
            font-size: 12px;
            padding: 6px 8px;
            margin-left: 5px;
        }

        .done-btn {
            background: #28ffbf;
        }

        .delete-btn {
            background: #ff4b5c;
            color: #fff;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(-10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>

<div class="todo-container">
    <h1>✨ Smart To-Do List ✨</h1>

    <div class="input-box">
        <input type="text" id="taskInput" placeholder="Enter your task...">
        <button onclick="addTask()">Add</button>
    </div>

    <ul id="taskList"></ul>
</div>

<script>
    function addTask() {
        const input = document.getElementById("taskInput");
        const taskText = input.value.trim();

        if (taskText === "") {
            alert("Please enter a task!");
            return;
        }

        const li = document.createElement("li");
        li.innerHTML = `
            <div class="task-info">
                <span class="status">⏳</span>
                <span class="task-number"></span>
                <span class="task-text">${taskText}</span>
            </div>
            <div class="actions">
                <button class="done-btn" onclick="markDone(this)">Done</button>
                <button class="delete-btn" onclick="deleteTask(this)">Delete</button>
            </div>
        `;

        document.getElementById("taskList").appendChild(li);
        input.value = "";

        updateNumbers();
    }

    function markDone(button) {
        const task = button.parentElement.parentElement;
        task.classList.toggle("completed");

        const status = task.querySelector(".status");
        status.textContent = task.classList.contains("completed") ? "✅" : "⏳";

        updateNumbers();
    }

    function deleteTask(button) {
        const task = button.parentElement.parentElement;
        task.remove();
        updateNumbers();
    }

    function updateNumbers() {
        const tasks = document.querySelectorAll("#taskList li");
        let count = 1;

        tasks.forEach(task => {
            const numberSpan = task.querySelector(".task-number");
            numberSpan.textContent = count + ".";
            count++;
        });
    }
</script>

</body>
</html>

<img width="1907" height="883" alt="image" src="https://github.com/user-attachments/assets/2a1aadd4-87a2-4741-869a-a1d36a168b40" />
<img width="1918" height="876" alt="image" src="https://github.com/user-attachments/assets/f894bffe-fd57-4060-a1a9-d8fa22675b67" />
<img width="1913" height="875" alt="image" src="https://github.com/user-attachments/assets/46a3223b-4246-41d1-a4dc-d2fa00fd4662" />





