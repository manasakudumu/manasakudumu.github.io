<script>
  import FadeIn from '../components/FadeIn.svelte';
  let hobbies = [
    {
      title: "dancing",
      description: "the best stress buster",
      icon: "dance.png",
    },
    {
      title: "rock climbing",
      description: "new heights and tiny holds",
      icon: "climb.png",
    },
    {
      title: "cafe hopping",
      description: "love my daily matcha :)",
      icon: "whisk.png",
    },
    {
      title: "reading",
      description: "i would love some recs!",
      icon: "book.png",
    }
  ];
</script>

<FadeIn>
<section class="about">
<div class="about-section">
  <div class="about-card">
    <img class="about-img" src="6C35.jpg" alt="Manasa by Waban Lake" />
    <div class="about-bio">
      <p>I'm a junior at Wellesley College majoring in Computer Science and Economics. My work focuses on the intersection of accessibility, AI, and inclusive design. I build research-informed tools and design experiences that empower underserved communities. </p>
      <p>Through research at Wellesley, I've explored how disabled users interact with large language models and contributed to work on equitable AI design. My academic background gives me a strong foundation, but much of my learning comes from real-world projects and self-driven exploration.</p>
      <p>I'm passionate about applying machine learning, computer vision, and human-centered design to solve societal challenges, one commit at a time.</p>
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
</div>
</section>
</FadeIn>

<style>

.about-section {
  margin: 0 auto;
  padding: 2rem 1rem 0 1rem;
  max-width: 900px;
}

.about-card {
  display: flex;
  align-items: center;
  gap: 2.5rem;
  margin-bottom: 3rem;
}

.about-img {
  width: 270px;
  height: 360px;
  object-fit: cover;
  border-radius: 16px;
  border: 3px solid #000000;
  background: #e7ecd6;
  box-shadow: 0 2px 18px 0 #6c7b3e13;
  display: block;
  max-width: 100%;
}


.about-bio {
  flex: 1;
  color: #6C7B3E;
  min-width: 230px;
}

.about-bio h2 {
  font-size: 2.1rem;
  font-weight: 800;
  color: #232a14;
  margin-bottom: 0.4rem;
  letter-spacing: -1px;
  font-family: 'Satoshi', Arial, sans-serif;
}

.about-bio h4 {
  font-size: 1.12rem;
  color: #6C7B3E;
  margin: 0 0 1em 0;
  font-weight: 600;
  font-family: 'Rubik', Arial, sans-serif;
}

.about-bio p {
  color: black;
  font-size: 1.08rem;
  margin-bottom: 0.65em;
  line-height: 1.7;
  font-family: 'Satoshi', Arial, sans-serif;
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
  gap: 1.1rem;
  justify-content: flex-start;
  margin-top: 0.2rem;
  flex-wrap: wrap;
}

.hobby-card {
  background: #d6e0ba;
  border-radius: 18px;
  padding: 1.2rem 1.2rem 1.8rem 1.2rem;
  width: 173.4px;
  min-height: 120px;
  display: flex;
  flex-direction: column;
  position: relative;
  overflow: visible;
}

.hobby-draw {
  position: absolute;
  left: 50%;
  bottom: -30px;
  transform: translateX(-20%);
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
  padding-right:5em;
}

@media (max-width: 800px) {
  .about-card {
    flex-direction: column;
    align-items: center;
    gap: 1.4rem;
    text-align: center;
  }
  .about-img {
    width: 180px;
    height: 240px;
  }
  .about-bio {
    min-width: unset;
  }
  .hobby-list {
    justify-content: center;
  }
  .hobby-card {
    width: 90vw;
    max-width: 330px;
    margin: 0 auto;
  }
  .hobby-draw {
    width: 120px;
    height: 120px;
    left: 50%;
    transform: translateX(-50%);
  }
}

</style>
