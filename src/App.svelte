<script>
  import Title from './lib/title.svelte'
  import Task from './lib/task.svelte'

  
</script>

<main>
  <!--Header at the top-->
  <header>
    <a class="logo" href='/'>ToDoer</a>
    <nav>
      <a href="/">Services</a>
      <a href="/">Projects</a>
      <a href="/">About</a>
      <button>Contact</button>
    </nav>
    <div class="hamburger">
      <span>X</span>
    </div>
    <div class="hamburger-menu">
      <ul>
        <li><a href="/">Services</a></li>
        <li><a href="/">Projects</a></li>
        <li><a href="/">About</a></li>
      </ul>
    </div>
  </header>

  <!--Body after the header-->

  <body>
    
    <Title />

    <Task />

  </body>

</main>

<style>

</style>