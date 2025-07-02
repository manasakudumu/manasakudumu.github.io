<script>
  import { onMount } from 'svelte';
  import { fade } from 'svelte/transition';
  import About from "../lib/About.svelte";
  import Experience from "../lib/Experience.svelte";
  import Footer from "../components/Footer.svelte";
  import Projects from "../lib/Projects.svelte";
  import Nav from "../components/Nav.svelte";
  import Connect from '../lib/Connect.svelte';

  let fullName ="Hello! I'm Manasa."
  let typedName = "";
  let index = 0;

  const typeWriter = () => {
    const interval = setInterval(() => {
      if (index < fullName.length) {
        typedName += fullName[index];
        index++;
      } else {
        clearInterval(interval);
      }
    }, 100);
  };

  onMount(() => {
    typeWriter();
  });

</script>

<div class="content-container">
  <Nav />
    

    <br>
    <h1 class="typing">{typedName}</h1>
    <p in:fade={{ duration: 900 }}>I am a rising junior at Wellesley College, double majoring in Computer Science and Economics. 
      My work explores how technology, AI, and inclusive design can empower people and communities. 
      My goal is to build accessible tech solutions that bridge gaps and create real impact. </p>

    <h2 id="experience">Experience</h2>
    <Experience />

    <h2 id="projects">Projects</h2>
    <Projects />

    <br id="about">
    <About />

    <h2 id="connect">Let's connect!</h2>
    <Connect />
    
</div>
<Footer />
