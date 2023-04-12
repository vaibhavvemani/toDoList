<script>
  import Title from './lib/title.svelte'
  import Task from './lib/task.svelte'
  let index = 0;
  const menu = [
    {burgerOn: false,displayStyle: 'none'},
    {burgerOn: true, displayStyle: 'flex'}
  ]
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
      <button class="menubutton" on:click={() => { index ? --index : ++index  }}>Menu</button>
    </div>
    <div class="hamburger-menu" style="display:{menu[index].displayStyle}">
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
  .menubutton {
    height: 2rem;
    width: 8rem;
    border: none;
    border-radius: 10px;
    background-image: linear-gradient(to right,#ff8a00,#c11063);
  }
</style>