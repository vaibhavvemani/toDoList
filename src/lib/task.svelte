<script>
    let tsk;
    let id = 1;
    let todos = []
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
            <li>
              <label for="task">{index+1} {todo.name}
                <input type='checkbox' checked={todo.completed} id='task'>
              </label>
            </li>
            {/each}
          </ul>
        </div>
        
      </div>

    <div class="input-container">
        <input type="text" bind:value={tsk} class="task-name" placeholder="type your task" >
    </div>
    
    <div class="add-container">
        <button class="add-task" on:click={addTask}>add task</button>
        <button class="remove-task" on:click={removeTask}>remove task</button>
    </div>
</main>

<style>
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