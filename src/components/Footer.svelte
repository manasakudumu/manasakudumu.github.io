<footer class="footer">
  <div class="footer-inner">
    <div class="footer-links">
      <a href="mailto:mk122@wellesley.edu">→Email</a>
      <a href="https://github.com/manasakudumu" target="_blank" rel="noopener">→GitHub</a>
      <a href="https://www.linkedin.com/in/manasa-kudumu-098670215/" target="_blank" rel="noopener">→LinkedIn</a>
      <a href="https://drive.google.com/file/d/1OcfVoHQUOa92jSDu0GewNy3o-p7VtDSA/view?usp=sharing" target="_blank" rel="noopener">→Resume</a>
    </div>
    <div class="footer-meta">
      <div>Updated 8/25</div>
      <div>©Manasa Kudumu_2025</div>
    </div>
  </div>
</footer>

<style>
  .footer {
  width: 100%;
  background: #eaeae3 url('bg.png') center 70% / 100% 200% no-repeat;
  border-top: 2px solid #232323;
  font-family: 'Inter', Arial, sans-serif;
  padding: 1.2rem 0;
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

.footer-links {
  display: flex;
  gap: 2rem;
}

.footer-links a {
  color: #232323;
  text-decoration: none;
  font-size: 1.18rem;
  transition: color 0.2s;
}

.footer-links a:hover {
  color: #6C7B3E;
  text-decoration: underline;
}

.footer-meta {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  color: #232323;
  font-size: 1rem;
  opacity: 0.93;
  gap: 0.5rem;
}

@media (max-width: 700px) {
  .footer-inner {
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    padding: 0 1rem;
  }
  .footer-links {
    justify-content: center;
    gap: 1rem;
    margin-bottom: 0.4rem;
  }
  .footer-meta {
    align-items: center;
    text-align: center;
    font-size: 0.98rem;
    margin-top: 0.4rem;
  }
}
</style>