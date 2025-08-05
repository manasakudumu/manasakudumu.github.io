<script>
  let activeSection = '';
</script>

<nav class="navbar">
  <div class="nav-inner">
    <div class="nav-left">
      <span class="site-name"><a href="#">Manasa Kudumu</a></span>
    </div>
    <ul class="links">
      <li><a href="#experience" class:active={activeSection === 'experience'} on:click={() => activeSection = 'experience'}>Experience</a></li>
      <li><a href="#projects" class:active={activeSection === 'projects'} on:click={() => activeSection = 'projects'}>Projects</a></li>
      <li><a href="#about" class:active={activeSection === 'about'} on:click={() => activeSection = 'about'}>About</a></li>
    </ul>
  </div>
  <div class="nav-border"></div>
</nav>



<style>
  .navbar {
    position: sticky;
    top: 0;
    background-color: #F9F9ED;
    z-index: 999;
    display: flex;
    flex-direction: column;
  }

  .nav-inner {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
  }

  .nav-border {
    width: 100%;
    height: 2px;
    background-color: #232323;
  }
  .links {
    display: flex;
    gap: 2rem;          
    list-style: none;  
    margin: 0;
    padding: 0;
    align-items: center;
  }
  .navbar .links a {
    position: relative;
    display: inline-block;
    color: #232323;
    text-decoration: none;
    padding: 0.5rem 0;
    transition: color 0.2s;
  }
  .navbar .links a::after {
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
  .navbar .links a:hover,
  .navbar .links a:focus {
    color: #6C7B3E;
  }
  .navbar .links a:hover::after,
  .navbar .links a:focus::after {
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
