<script>
  import { onMount } from 'svelte';
  import { fade } from 'svelte/transition';
  import Nav from "../components/Nav.svelte";
  import Footer from "../components/Footer.svelte";
  import Experience from "../lib/Experience.svelte";
  import Projects from "../lib/Projects.svelte";
  import About from "../lib/About.svelte";
  import Connect from "../lib/Connect.svelte";
  import Landing from '../components/Landing.svelte';

  let scrollProgress = 0;

  function updateScrollProgress() {
    const scrollTop = window.scrollY;
    const docHeight = document.body.scrollHeight - window.innerHeight;
    scrollProgress = docHeight > 0 ? (scrollTop / docHeight) * 100 : 0;
  }

  onMount(() => {
    window.addEventListener('scroll', updateScrollProgress);
    return () => window.removeEventListener('scroll', updateScrollProgress);
  });
</script>

<div class="progress-container">
  <div class="progress-bar" style="width: {scrollProgress}%"></div>
</div>

<Nav />

<Landing />

<div class="sections">
  <h2 id="experience"> Experience </h2>
  <Experience />

  <h2 id="projects"> Projects </h2>
  <Projects />

  <div class=about-part>
    <h2 id="about">It's nice to meet you!</h2>
    <About />
  </div>

  <br>
  <br>

  <!-- <br id="connect">
  <Connect /> -->
</div>
<br>
<Footer />

<style>
:global(body) {
  margin: 0;
  padding: 0;
  background: #F6F9ED;
  font-family: 'Inter', Arial, sans-serif;
}

h2{
  text-align: center;
}

.sections {
  margin-top: 6rem;
  max-width: 2000px;
  padding: 2rem 2.5rem;
  margin-left: auto;
  margin-right: auto;
  background: transparent;
}

.progress-container {
  width: 100%;
  height: 5px;
  background: transparent;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 2000;
}

.progress-bar {
  height: 100%;
  background: #6C7B3E;
  width: 0;
  border-radius: 2px;
}

</style>
