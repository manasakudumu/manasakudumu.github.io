<script>
    import { onMount } from 'svelte';
  
    let visible = false;
    let element;
  
    onMount(() => {
      const observer = new IntersectionObserver(
        ([entry]) => {
          if (entry.isIntersecting) {
            visible = true;
            observer.unobserve(entry.target); // fade in only once
          }
        },
        {
          threshold: 0.1
        }
      );
  
      observer.observe(element);
    });
  </script>
  
  <div bind:this={element} class:visible class="fade-section">
    <slot />
  </div>
  
  <style>
    .fade-section {
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.8s ease-out, transform 0.8s ease-out;
    }
  
    .fade-section.visible {
      opacity: 1;
      transform: translateY(0);
    }
  </style>
  