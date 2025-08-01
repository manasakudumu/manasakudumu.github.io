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
  let typewriterTimeout = null;

  let bostonTime = "";

  function updateBostonTime() {
    bostonTime = new Date().toLocaleTimeString("en-US", {
      timeZone: "America/New_York",
      hour: '2-digit',
      minute: '2-digit',
      second: '2-digit'
    });
  }

  function typeWriter() {
    if (typing) {
      if (charIndex < messages[messageIndex].length) {
        typedName += messages[messageIndex][charIndex];
        charIndex++;
        typewriterTimeout = setTimeout(typeWriter, 60);
      } else {
        typing = false;
        if (isPlaying) {
          typewriterTimeout = setTimeout(typeWriter, 1500);
        }
      }
    } else if (isPlaying) {
      if (charIndex > 0) {
        typedName = typedName.slice(0, -1);
        charIndex--;
        typewriterTimeout = setTimeout(typeWriter, 30);
      } else {
        typing = true;
        messageIndex = (messageIndex + 1) % messages.length;
        typewriterTimeout = setTimeout(typeWriter, 0);
      }
    }
  }

  function handlePlayPause() {
    isPlaying = !isPlaying;
    if (isPlaying && !typing && charIndex === messages[messageIndex].length) {
      typewriterTimeout = setTimeout(typeWriter, 1500);
    }
  }

  onMount(() => {
    typeWriter();
    updateBostonTime();
    const interval = setInterval(updateBostonTime, 1000);
    return () => {
      if (typewriterTimeout) clearTimeout(typewriterTimeout);
      clearInterval(interval);
    };
  });
</script>
<FadeIn>
<div class="landing" transition:fade>
  <div class="intro-block">
    <span class="heading-placeholder">Hello! I'm Manasa.</span>
    <div class="boston-row">
      <span>Based in Boston <span class="arrow">→</span></span>
      <span class="boston-time">{bostonTime}</span>
    </div>
    <h1 class="typing">{typedName}</h1>
    <p>a multidisciplinary developer studying Computer Science + Economics @ Wellesley College and MIT</p>
    <h5>(my portfolio is currently a work in progress!)</h5>
  </div>
    <button class="typewriter-toggle" on:click={handlePlayPause} aria-label={isPlaying ? 'Pause typewriter' : 'Play typewriter'}>
      {#if isPlaying}
        ⏸️
      {:else}
        ▶️
      {/if}
    </button>  
</div>
</FadeIn>


<style>
.landing {
  min-height: 85vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
  text-align: left;
  padding: 2.5rem 7rem 0 7rem;
  background: #f6f9ed url('bg.png') right center/cover no-repeat;
  background-attachment: local;
  background-blend-mode: normal;
}

.intro-block {
  max-width: 720px;
  width: 100%;
  margin-left: 3rem;
  margin-top: 2rem;
}

.boston-row {
  font-size: 1.1rem;
  font-weight: 500;
  color: #485935;
  margin-bottom: 0.6em;
  letter-spacing: 0.01em;
  display: flex;
  align-items: baseline;
  gap: 1.1em;
}

.boston-row .arrow {
  font-weight: 600;
  margin: 0 0.17em 0 0.19em;
  font-size: 1.1em;
}

.boston-time {
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

@media (max-width: 700px) {
  .typing { font-size: 2.3rem; }
  .landing { min-height: 70vh; padding-top: 1.5rem; }
}

.typewriter-toggle {
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

.typewriter-toggle:hover {
  background: #f6f9ed;
}
</style>
