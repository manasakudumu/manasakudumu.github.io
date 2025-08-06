<script>
    import { onMount } from 'svelte';
    let visible = false;
    let element;
    onMount(() => {
      const observer = new IntersectionObserver(
        ([entry]) => {
          if (entry.isIntersecting) {
            visible = true;
            observer.unobserve(entry.target); 
          }
        },
        {
          threshold: 0.1
        }
      );
      observer.observe(element);
    });
</script>
<div class="fade" bind:this={element} class:visible>
  <slot />
</div>
<style>
  .fade {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.8s ease-out, transform 0.8s ease-out;
  }
  .fade.visible {
    opacity: 1;
    transform: translateY(0);
  }
</style>
  