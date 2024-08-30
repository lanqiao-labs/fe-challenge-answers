```js
    const addTaskBtn = document.getElementById('add-task-btn');
    const taskInput = document.getElementById('new-task');
    const taskList = document.getElementById('task-list');

    loadTasks();

    // Add task event listener
    addTaskBtn.addEventListener('click', function () {
        const taskText = taskInput.value.trim();
        if (taskText === '') {
            return; 
        }
        addTask({'text':taskText,'checked':false});
        taskInput.value = ''; 
    });


   //统计任务
    function addTask(task) {
        const li = document.createElement('li');

        const checked=task.checked?'checked':'';
        const spanClass=task.checked?'class="done"':'';
        
        li.innerHTML=`<input type='checkbox' onclick='doneTask(this)' ${checked} /><span ${spanClass}>${task.text}</span><button class='delBtn' onclick='removeTask(this)'>删除</button>`

        taskList.appendChild(li);

        saveTasks(); 
    }

    //完成任务
    function doneTask(ck){
        ck.nextSibling.classList.toggle('done');
        saveTasks(); 
    }

    //删除任务
    function removeTask(btn){
        taskList.removeChild(btn.parentNode);
        saveTasks();
    }

    // 保存任务清单到localStorage
    function saveTasks() {
        const tasks = [];
        taskList.querySelectorAll('li').forEach(li => {
            const ck=li.querySelector('input');
            tasks.push({'text':li.textContent.replace('删除', '').trim(),'checked':ck.checked});
        });
        localStorage.setItem('tasks', JSON.stringify(tasks));
    }

    // 从localStorage中读取任务清单
    function loadTasks() {
        const tasks = JSON.parse(localStorage.getItem('tasks')) || [];
        tasks.forEach(task => {
            addTask(task);
        });
    }

```