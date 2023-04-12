<script>
    let tsk;
    let id = 1;
    let todos = []
    let changeOpac;
    $: opacity = changeOpac ? '0.6' : '1';
    function addTask() {
        todos.push({id: id++, name: tsk, completed: false})
        todos = todos;
    }

    function removeTask() {
        todos.pop();
        todos = todos;
    }
    
</script>

<main>
    <div class="task-container">

        <div class="tasks">
          <ul>
            {#each todos as todo, index (todo.id)}
            <li class:done={todo.completed}>
                <div class="animation">
                    <label for="task" >{index+1} {todo.name}
                        <input  type='checkbox' bind:checked={todo.completed} id='task'  >
                    </label>
                </div>
            </li>
            {/each}
          </ul>

        </div>
        
      </div>

    <div class="input-container">
        <input id="taskInput" type="text" bind:value={tsk} class="task-name" placeholder="type your task" required>
    </div>
    
    <div class="add-container">
        <button class="add-task" on:click={addTask}>add task</button>
        <button class="remove-task" on:click={removeTask}>remove task</button>
    </div>
</main>

<style>
    @keyframes fromTheRight {
        from {
            transform: translateX(-1000px);
        }
        to {
            transfrom: translateX(0px);
        }
    }

    .done {
        opacity: 0.6;
    }

    .animation {
        animation: fromTheRight 0.2s ease-out;
    }
    .task-container {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 20rem;
        
    }

    .tasks {
        position:static;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
        width: 20rem;
        box-shadow: 0px 0px 30px 10px #191919;
        overflow-y: auto;
    }

    .tasks ul {
        list-style: none;
    }

    label {
        margin: 1rem;
    }
    .input-container{
        display: flex;
        justify-content: center;
        margin: 20px
    }

    .input-container input {
        height: 2rem;
        width: 10rem;
        padding: 0 5px;
        border: #191919 solid 1px;
        background-color: #202020;
        transition: width 0.4s ease;
        text-align: center;
    }

    .input-container input:hover, .input-container input:focus {
        width: 20rem;
        border-radius: 20px;
        box-shadow: 5px 5px 10px #303030, -5px -5px 10px #161616;

    }

    .add-container {
        display: flex;
        justify-content: center;
        margin: 30px
    }

    .add-container button {
        width: 10rem;
        height: 2rem;
        margin: 5px;
        border: none;
        border-radius: 10px;
        background-color: #191919;
        background-image: linear-gradient(to right, #ff8a00, #c11063);
        background-size: 0 100%;
        background-repeat: no-repeat;
        transition: 0.4s;
    }

    .add-container button:hover {
        background-size: 100% 100%;
    }
</style>