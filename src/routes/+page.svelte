<script>
  import { onMount } from 'svelte';
  import Nav from "../components/Nav.svelte";
  import Footer from "../components/Footer.svelte";
  import Experience from "../components/Experience.svelte";
  import Projects from "../components/Projects.svelte";
  import About from "../components/About.svelte";
  import Connect from "../components/Connect.svelte";
  import Landing from '../components/Landing.svelte';
  import FadeIn from '../components/FadeIn.svelte';
  
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
<FadeIn>
<Nav />

<Landing />

<br id="experience">
<br>
<br>
<h2 > Experience </h2>
<Experience />

<br id="projects">
<br>
<h2> Projects </h2>
<Projects />

<br>
<br>
<h2 id="about">It's nice to meet you!</h2>
<About />

<br id="connect">
<br>
<!-- <br>
<h2> Let's connect </h2>
<Connect /> -->
<br>
<br>
<br>

<Footer />
</FadeIn>
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
