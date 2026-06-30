<script>
  import { onMount } from "svelte";
  export let playClickSound = () => {};
  let activeSection = "experience";
  onMount(() => {
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            activeSection = entry.target.id;
          }
        });
      },
      {threshold: 0.4}
    );
    ["experience", "research", "projects", "about"].forEach((id) => {
      const section = document.getElementById(id);
      if (section) observer.observe(section);
    });
    return () => observer.disconnect();
  });
</script>
<nav class="navbar">
  <div class="nav-inner">
    <div class="nav-left">
      <span class="site-name">
        <a href="#" on:click={playClickSound}>
          Manasa Kudumu
        </a>
      </span>
    </div>
    <ul class="links">
      <li><a href="#experience" class:active={activeSection === "experience"} on:click={playClickSound}>Experience</a></li>
      <li><a href="#research" class:active={activeSection === "research"} on:click={playClickSound}>Research</a></li>
      <li><a href="#projects" class:active={activeSection === "projects"} on:click={playClickSound}>Projects</a></li>
      <li><a href="#about" class:active={activeSection === "about"} on:click={playClickSound}>About</a></li>
      <li><a href="https://drive.google.com/file/d/151vWr-nDxFcxRiEkzgkeY5IPg-A-BsZY/view?usp=sharing" target="_blank" on:click={playClickSound}>Resume</a></li>
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
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 2.5px;
    background: #83943d;
    border-radius: 2px;
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.35s cubic-bezier(.77,0,.18,1);
  }
  .navbar .links a:hover,
  .navbar .links a:focus,
  .navbar .links a.active {
    color: #6C7B3E;
  }
  .navbar .links a:hover::after,
  .navbar .links a:focus::after,
  .navbar .links a.active::after {
    transform: scaleX(1);
  }
  .nav-left a {
    color: #83943d;
    font-weight: 900;
    font-size: 1.35rem;
    font-family: "Satoshi", Arial, sans-serif;
    text-decoration: none;
    letter-spacing: -0.5px;
  }
  .nav-border {
    width: 100%;
    height: 2px;
    background-color: #232323;
  }
  @media (max-width: 768px) {
  .nav-inner {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.75rem;
    padding: 1rem;
  }
  .links {
    width: 100%;
    gap: 1rem;
    overflow-x: auto;
    white-space: nowrap;
    scrollbar-width: none;
  }
  .links::-webkit-scrollbar {
    display: none;
  }
  .nav-left a {
    font-size: 1.25rem;
  }
  .navbar .links a {
    font-size: 0.95rem;
  }
}
</style>