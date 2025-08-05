<script>
  import FadeIn from '../components/FadeIn.svelte';
  let hobbies = [
    { title: "dancing", description: "the best stress buster, hands down", icon: "dance.png" },
    { title: "rock climbing", description: "reaching new heights and tiny holds", icon: "climb.png" },
    { title: "cafe hopping", description: "i love my daily matcha + bagel combo <3", icon: "whisk.png" },
    { title: "reading", description: "currently into jefferey archer and murakami", icon: "book.png" },
    // { title: "reading", description: "i would love some recs!", icon: "book.png" }
  ];
</script>

<FadeIn>
  <section class="about-section">
    <div class="about-card">
      <img class="about-img" src="6C35.jpg" alt="Manasa by Waban Lake" />
      <div class="about-bio">
        <p>I'm a junior at Wellesley College majoring in Computer Science and Economics. My work focuses on the intersection of accessibility, AI, and inclusive design. I build research-informed tools and design experiences that empower underserved communities.</p>
        <p>Through research at Wellesley, I've explored how disabled users interact with large language models and contributed to work on equitable AI design. My academic background gives me a strong foundation, but much of my learning comes from real-world projects and self-driven exploration.</p>
        <p>I'm passionate about applying machine learning, computer vision, and human-centered design to solve societal challenges, one commit at a time. I'm also deeply interested in linguistics, quantitative economics, and financial systems, especially how NLP and AI can reshape decision-making, unlock equitable access to financial tools, and bridge the gap between human and machine understanding. In the future, I want to work on problems that sit at the intersection of language, intelligence, and economic behavior, building models that are not only technically robust but also socially aware.</p>
      </div>
    </div>
    <div class="hobbies">
      <h3>I'm also into...</h3>
      <div class="hobby-list">
        {#each hobbies as hobby}
          <div class="hobby-card">
            <div class="hobby-title">{hobby.title}</div>
            <div class="hobby-desc">{hobby.description}</div>
            <img class="hobby-draw" src={hobby.icon} alt={hobby.title + ' illustration'} />
          </div>
        {/each}
      </div>
    </div>
  </section>
</FadeIn>

<style>
  .about-section {
    padding: 2rem 10rem;          
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    /* gap: 1rem; */
    font-family: 'Satoshi', Arial, sans-serif;
  }
  .about-card {
    display: flex;
    align-items: center;
    gap: 2.5rem;
  }
  .about-img {
    width: 300px;
    height: 370px;
    object-fit: cover;
    border-radius: 16px;
    border: 3px solid #000;
    background: #e7ecd6;
    box-shadow: 0 2px 18px rgba(108,123,62,0.08);
  }
  .about-bio {
    flex: 1;
    color: #333;
    min-width: 230px;
  }
  .about-bio p {
    margin-bottom: 0.8em;
    line-height: 1.7;
    font-size: 1.05rem;
  }
  .hobbies {
    margin: 3rem 0 0 0;
    text-align: left;
    padding: 0;
    max-width: 100%;
  }
  .hobbies h3 {
    color: #6C7B3E;
    font-family: 'Satoshi', Arial, sans-serif;
    margin-bottom: 2rem;
  }
  .hobby-list {
    display: flex;
    gap: 1.5rem;
    justify-content: flex-start;
    margin-top: 0.2rem;
    flex-wrap: wrap;
  }
  .hobby-card {
    background: #d6e0ba;
    border-radius: 18px;
    padding: 1.2rem 1.2rem 1.8rem 1.2rem;
    width: 220px;
    min-height: 140px;
    display: flex;
    flex-direction: column;
    position: relative;
    overflow: visible;
  }
  .hobby-draw {
    position: absolute;
    left: 50%;
    bottom: -30px;
    transform: translateX(-10%);
    width: 150px;
    height: 150px;
    object-fit: contain;
    opacity: 1;
    pointer-events: none;
    z-index: 2;
  }
  .hobby-title {
    font-family: 'Rubik', 'Inter', Arial, sans-serif;
    font-weight: 500;
    font-size: 1.5rem;
    color: #697741;
    margin-bottom: 0.4rem;
  }
  .hobby-desc {
    font-family: 'Satoshi', Arial, sans-serif;
    font-size: 0.97rem;
    color: #757a6b;
    margin-bottom: 0.4rem;
    padding-right:7em;
  }
</style>
