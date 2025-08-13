<script>
  import { onMount } from 'svelte';
  import { fade } from 'svelte/transition';
  import FadeIn from '../components/FadeIn.svelte';
  const messages = [
    "Hello, I'm Manasa.",
    "வணக்கம், நான் மானசா.",
    "नमस्ते, मैं मानसा हूं।",
  ];
  let messageIndex = 0;
  let typedName = "";
  let charIndex = 0;
  let typing = true;
  let isPlaying = false;     
  let helloTimeout = null;
  let bosTime = "";
  function updateTime() {
    bosTime = new Date().toLocaleTimeString("en-US", {
      timeZone: "America/New_York",
      hour: '2-digit',
      minute: '2-digit',
      second: '2-digit'
    });
  }
  function schedule(ms) {
    if (helloTimeout) clearTimeout(helloTimeout);
    helloTimeout = setTimeout(hello, ms);
  }
  function hello() {
    if (typing) {
      if (charIndex < messages[messageIndex].length) {
        typedName += messages[messageIndex][charIndex++];
        schedule(60);
      } else {
        typing = false;
        schedule(1500); 
      }
      return;
    }
    if (!isPlaying) return;       
    if (charIndex > 0) {
      typedName = typedName.slice(0, -1);
      charIndex--;
      schedule(30);
    } else {
      typing = true;
      messageIndex = (messageIndex + 1) % messages.length;
      schedule(0);
    }
  }
  function handlePlay() {
    isPlaying = !isPlaying;
    if (isPlaying) {
      hello();
    } else {
      if (!typing && helloTimeout) clearTimeout(helloTimeout);
    }
  }
  onMount(() => {
    hello(); 
    updateTime();
    const interval = setInterval(updateTime, 1000);
    return () => {
      if (helloTimeout) clearTimeout(helloTimeout);
      clearInterval(interval);
    };
  });
</script>
<FadeIn>
  <div class="landing" transition:fade>
    <img src="bg.png" alt="background" class="bg-img" />
    <div class="intro-block">
      <span class="heading-placeholder">Hello! I'm Manasa.</span>
      <div class="bos-row">
        <span>Based in Boston <span class="arrow">→</span></span>
        <span class="bos-time">{bosTime}</span>
      </div>
      <hr class="line">
      <h1 class="typing">{typedName}</h1>
      <p class="subheading">
        a <em>multidisciplinary developer and researcher</em><br/> studying 
        <a href="https://www.wellesley.edu/academics/department/computer-science" target="_blank" rel="noopener">Computer Science</a> +
        <a href="https://www.wellesley.edu/academics/department/economics" target="_blank" rel="noopener">Economics</a> @ Wellesley College<br/>
        <span class="crossreg">cross-registered in 
          <a href="https://www.eecs.mit.edu/" target="_blank" rel="noopener">EECS</a> @ Massachusetts Institute of Technology
        </span>
      </p>
    </div>
    <button class="hello-toggle" on:click={handlePlay} aria-label={isPlaying ? 'Pause hello' : 'Play hello'}>
      {#if isPlaying}
        ⏸️
      {:else}
        ▶️
      {/if}
    </button>  
  </div>
</FadeIn>
<hr class="landing-bottom-line" />

<style>
  .landing {
    position: relative;
    min-height: 85vh;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    text-align: left;
    padding: 2.5rem 7rem 0 7rem;
    background-attachment: local;
    background-blend-mode: normal;
    overflow: hidden; 
  }
  .bg-img {
    position: absolute;
    top: 0;
    left: 0; 
    height: 100%;
    width: 100%; 
    z-index: -1;
    pointer-events: none;
  }
  .intro-block {
    max-width: 720px;
    width: 100%;
    margin-left: 3rem;
    margin-top: 2rem;
  }
  .bos-row {
    font-size: 1.1rem;
    font-weight: 500;
    color: #485935;
    margin-bottom: 0.6em;
    letter-spacing: 0.01em;
    display: flex;
    align-items: baseline;
    gap: 1.1em;
  }
  .bos-row .arrow {
    font-weight: 600;
    margin: 0 0.17em 0 0.19em;
    font-size: 1.1em;
  }
  .bos-time {
    color: #485935;
    letter-spacing: 0.06em;
    font-size: 1.08em;
  }
  .heading-placeholder {
    visibility: hidden;
    display: block;
    pointer-events: none;
    user-select: none;
    font-size: 4rem;
    font-weight: 700;
    font-family: inherit;
    margin-bottom: 1.3rem;
  }
  .typing {
    font-size: 4rem;
    font-weight: 700;
    color: #6C7B3E;
    margin-bottom: 1.3rem;
    letter-spacing: -1px;
    min-height: 4.5rem;
  }
  .hello-toggle {
    position: fixed;
    bottom: 2rem;
    right: 2rem;
    z-index: 1001;
    border: 1px solid #bbb;
    border-radius: 50%;
    padding: 1rem 1.1rem;
    font-size: 1.7rem;
    cursor: pointer;
    transition: background 0.2s;
  }
  .hello-toggle:hover {
    background: #d6e0ba;
  }
  .subheading {
    margin-top: 1rem;
    font-size: 1.25rem;
    line-height: 1.6;
    color: #333;
    font-family: 'Satoshi', Arial, sans-serif;
    max-width: 680px;
  }
  .subheading em {
    font-style: italic;
    color: #485935;
  }
  .subheading a {
    color: inherit;         
    font-weight: inherit;   
    text-decoration: underline;
  }
  .subheading a:hover {
    text-decoration: underline;
    color: #6C7B3E;
  }
  .line{
    height: 1px;              
    background-color: #000;   
    border: none;
    margin: 1.5rem 0;
  }
  .landing-bottom-line {
    height: 2px;
    background-color: #232323;
    border: none;
    width: 100%;
    margin: 0;
  }
  @media (max-width: 1024px) {
    .landing {
      padding: 2rem 3rem 0 3rem;
    }
    .intro-block {
      margin-left: 0;
      margin-top: 1rem;
    }
    .typing {
      font-size: 3rem;
      min-height: 3.5rem;
    }
    .heading-placeholder {
      font-size: 3rem;
    }
    .subheading {
      font-size: 1.1rem;
    }
  }
  @media (max-width: 768px) {
    .landing {
      padding: 2rem 2rem 0 2rem;
    }
    .typing {
      font-size: 2.2rem;
      min-height: 2.5rem;
    }
    .heading-placeholder {
      font-size: 2.2rem;
    }
    .subheading {
      font-size: 1rem;
      line-height: 1.5;
    }
    .bos-row {
      flex-direction: column;
      align-items: flex-start;
      gap: 0.3em;
    }
    .hello-toggle {
      bottom: 1rem;
      right: 1rem;
      padding: 0.8rem 0.9rem;
      font-size: 1.4rem;
    }
  }
  @media (max-width: 480px) {
    .landing {
      padding: 1.5rem 1rem 0 1rem;
    }
    .typing {
      font-size: 1.8rem;
      min-height: 2rem;
    }

    .heading-placeholder {
      font-size: 1.8rem;
    }
    .subheading {
      font-size: 0.95rem;
    }
    .hello-toggle {
      font-size: 1.2rem;
      padding: 0.6rem 0.7rem;
    }
  }
</style>
