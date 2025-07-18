<script>
  let activeSection = '';
</script>

<nav class='navbar'>
    <div class="nav-left">
        <span class="site-name"><a href="#">Manasa Kudumu</a></span>
    </div>
    <ul class="nav-links">
        <li><a href="#about" class:active={activeSection === 'about'} on:click={() => activeSection = 'about'}>About</a></li>
        <li><a href="#experience" class:active={activeSection === 'experience'} on:click={() => activeSection = 'experience'}>Experience</a></li>
        <li><a href="#projects" class:active={activeSection === 'projects'} on:click={() => activeSection = 'projects'}>Projects</a></li>
        <li><a href="#connect" class:active={activeSection === 'connect'} on:click={() => activeSection = 'connect'}>Connect</a></li>
    </ul>
</nav>

<style>
    .navbar {
        position: sticky;
        top: 0;
        background-color: #edf0e4;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1rem 2rem;
    }

    .nav-links {
      display: flex;
      gap: 2rem;          
      list-style: none;  
      margin: 0;
      padding: 0;
      align-items: center;
    }

    .navbar .nav-links a {
      position: relative;
      display: inline-block;
      color: #232323;
      text-decoration: none;
      padding: 0.5rem 0;
      transition: color 0.2s;
    }

    .navbar .nav-links a::after {
      content: "";
      display: block;
      position: absolute;
      left: 0; bottom: 0;
      height: 2.5px;
      width: 100%;
      background: #83943d;
      border-radius: 2px;
      transform: scaleX(0);
      transform-origin: left;
      transition: transform 0.35s cubic-bezier(.77,0,.18,1);
    }

    .navbar .nav-links a:hover,
    .navbar .nav-links a:focus {
      color: #6C7B3E;
    }

    .navbar .nav-links a:hover::after,
    .navbar .nav-links a:focus::after {
      transform: scaleX(1);
    }

    .navbar .nav-links a.active,
    .navbar .nav-links a[aria-current="page"] {
      color: #83943d;
    }

    .navbar .nav-links a.active::after,
    .navbar .nav-links a[aria-current="page"]::after {
      transform: scaleX(1);
    }

    .nav-left a {
      color: #83943d;
      font-weight: 900;
      font-size: 1.35rem;
      font-family: 'Satoshi', Arial, sans-serif;
      text-decoration: none;
      letter-spacing: -0.5px;
    }
</style>
