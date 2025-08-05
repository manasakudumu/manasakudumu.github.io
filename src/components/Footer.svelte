<script>
  import FadeIn from "./FadeIn.svelte";
</script>

<FadeIn>
  <footer class="footer">
    <img src="bg.png" alt="footer background" class="footer-img" />
    <div class="footer-inner">
      <div class="links">
        <a href="mailto:mk122@wellesley.edu">→Email</a>
        <a href="https://github.com/manasakudumu" target="_blank" rel="noopener">→GitHub</a>
        <a href="https://www.linkedin.com/in/manasa-kudumu-098670215/" target="_blank" rel="noopener">→LinkedIn</a>
        <a href="https://drive.google.com/file/d/1OcfVoHQUOa92jSDu0GewNy3o-p7VtDSA/view?usp=sharing" target="_blank" rel="noopener">→Resume</a>
      </div>
      <div class="meta">
        <div>Updated 8/25</div>
        <div>©Manasa Kudumu_2025</div>
      </div>
    </div>
  </footer>
</FadeIn>

<style>
  .footer {
    position: relative;
    width: 100%;
    border-top: 2px solid #232323;
    font-family: 'Inter', Arial, sans-serif;
    padding: 1.2rem 0;
    overflow: hidden;
  }
  .footer-img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: -1;
    pointer-events: none;
  }
  .footer-inner {
    max-width: 1000px;
    margin: 0 auto;
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    width: 100%;
    padding: 0 2rem;
  }
  .links {
    display: flex;
    gap: 2rem;
  }
  .links a {
    color: #232323;
    text-decoration: none;
    font-size: 1.18rem;
    transition: color 0.2s;
  }
  .links a:hover {
    color: #6C7B3E;
    text-decoration: underline;
  }
  .meta {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    color: #232323;
    font-size: 1rem;
    opacity: 0.93;
    gap: 0.5rem;
  }
</style>
