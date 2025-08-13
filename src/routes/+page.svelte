<script>
  import { onMount } from 'svelte';
  import Nav from "../components/Nav.svelte";
  import Footer from "../components/Footer.svelte";
  import Experience from "../components/Experience.svelte";
  import Projects from "../components/Projects.svelte";
  import About from "../components/About.svelte";
  import Landing from '../components/Landing.svelte';
  import FadeIn from '../components/FadeIn.svelte';
  let scrollProgress = 0;
  let numImages = 0;
  let clickSound;
  function playClickSound() {
    if (clickSound) {
      clickSound.currentTime = 0;
      clickSound.play();
    }
  }
  function updateScrollProgress() {
    const scrollTop = window.scrollY;
    const docHeight = document.body.scrollHeight - window.innerHeight;
    scrollProgress = docHeight > 0 ? (scrollTop / docHeight) * 100 : 0;
  }
  onMount(() => {
    window.addEventListener('scroll', updateScrollProgress);
    const content = document.querySelector('.content-before-footer');
    const imageHeight = 300;
    if (content) {
      const contentHeight = content.offsetHeight;
      numImages = Math.ceil(contentHeight / imageHeight);
    }
    return () => window.removeEventListener('scroll', updateScrollProgress);
  });
</script>

<audio bind:this={clickSound} src="/sounds/click.mp3" preload="auto"></audio>
<Nav {playClickSound} />
<div class="progress-container">
  <div class="progress-bar" style="width: {scrollProgress}%"></div>
</div>
<div class="content-before-footer">
  <div class="bg-img-wrapper">
    {#each Array(numImages) as _, i}
      <img src="/check.png" alt="grainy grid background" class="bg-img" />
    {/each}
  </div>
  <FadeIn>
    <Landing />
  </FadeIn>
  <div class="background-wrapper">
    <br id="experience"><br>
    <h2>Experience</h2>
    <Experience />
    <br id="projects"><br>
    <h2>Projects</h2>
    <Projects />
    <br id="about"><br>
    <h2>It's nice to meet you!</h2>
    <About />
    <br id="connect"><br><br><br>
  </div>
</div>
<FadeIn>
  <Footer />
</FadeIn>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
    background: #F6F9ED;
    font-family: 'Inter', Arial, sans-serif;
    position: relative;
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
  .background-wrapper {
    padding: 2rem 0;
  }
  .bg-img-wrapper {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -100;
    pointer-events: none;
    overflow: hidden;
  }
  .content-before-footer {
    position: relative;
    z-index: 1;
  }
  .bg-img {
    width: 100%;
    display: block;
    opacity: 0.6;
  }
  h2 {
    text-align: center;
  }
</style>
