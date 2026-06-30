<script>
  import FadeIn from '../components/FadeIn.svelte';

  const research = [
    {
      year: "2026",
      title: "Block Me from Myself: Adversarial Self-Use in Digital Overuse Recovery Narratives from r/nosurf",
      status: "Accepted Poster",
      venue: "International Conference on Computational Social Science (IC2S2 2026) | Burlington, VT",
      tags: ["Computational Social Science", "Digital Wellbeing", "Human-AI Interaction"],
      desc: "Investigated how people attempt to reduce digital overuse by analyzing over 9,900 r/nosurf posts. Using sentence embeddings, clustering, and qualitative analysis, we identified recurring recovery strategies and introduced the concept of adversarial self-use where individuals anticipate and circumvent their own attempts to limit technology use.",
      links: [
        { label: "Program Listing", url: "https://ic2s2-2026.org/program/" },
        { label: "Github", url: "https://github.com/manasakudumu/nosurf-computational-analysis/tree/main"}
      ]
    },
    {
      year: "2025",
      title: "What Financial Language Reveals About Consumer Confidence on Reddit",
      status: "Course Research Project",
      venue: "CS333: Natural Language Processing",
      tags: ["NLP", "Sentiment Analysis", "Finance", "Computational Social Science"],
      desc: "Built an NLP pipeline comparing FinBERT, VADER, and uncertainty-based language signals to investigate whether Reddit financial discourse can reflect consumer confidence and macroeconomic indicators.",
      links: [
        { label: "Paper", url: "https://drive.google.com/file/d/12CM-VozvzhEXBkKEHIBPhoEE1_qT0ZQ8/view?usp=sharing" },
        { label: "GitHub", url: "https://github.com/manasakudumu/consumer-confidence-reddit" }
      ]
    },
    {
      year: "2025",
      title: "Characterizing Uses and Prompting Strategies of LLM-Based Chatbots Among Neurodivergent Individuals",
      status: "Published Poster",
      venue: "ACM SIGACCESS Conference on Computers and Accessibility (ASSETS 2025) | Denver, CO",
      tags: ["Accessibility", "Human-AI Interaction", "LLMs"],
      desc: "Studied how neurodivergent individuals use and prompt LLM-based chatbots, focusing on accessibility, everyday support, and interaction patterns.",
      links: [
        { label: "View Publication", url: "https://dl.acm.org/doi/10.1145/3663547.3759721" },
        { label: "PDF", url: "https://dl.acm.org/doi/pdf/10.1145/3663547.3759721" }
      ]
    },
    {
      year: "2025",
      title: "Personalized Recommender Systems: Algorithms and Ethical Challenges in Health and Finance",
      status: "Course Research Paper",
      venue: "CS231 Fundamental Algorithms",
      tags: ["Algorithms", "Ethics", "Recommender Systems", "AI"],
      desc: "Surveyed recommendation systems in portfolio management, diet planning, and mental health prediction, analyzing their algorithmic foundations and ethical risks in sensitive decision-making contexts.",
      links: [
        { label: "Paper", url: "https://drive.google.com/file/d/1zL4vB2Bzj49NhcXYfAbv4WaEehCu1Uww/view?usp=sharing" }
      ]
    },
    {
      year: "2024",
      title: "“I’m treating it kind of like a diary”: Characterizing How Users with Disabilities Use AI Chatbots",
      status: "Published Extended Abstract",
      venue: "ACM SIGACCESS Conference on Computers and Accessibility (ASSETS 2024) | St. Johns, Canada",
      award: "2nd Place Undergraduate Student Research Competition",
      tags: ["Accessibility", "HCI", "Generative AI"],
      desc: "Investigated how people with disabilities integrate AI chatbots into daily life through interviews, diary studies, and qualitative analysis.",
      links: [
        { label: "View Publication", url: "https://dl.acm.org/doi/10.1145/3663548.3688549" },
        {label: "PDF",  url: "https://dl.acm.org/doi/pdf/10.1145/3663548.3688549"}
      ]
    }
  ];
</script>

<FadeIn>
  <section class="research-section">
    <div class="research-intro">
      <p>My research sits at the intersection of accessibility, human-AI interaction, computational social science, and natural language processing. By combining computational methods with human-centered research, I study how people interact with AI and design intelligent systems that are more inclusive and trustworthy.</p>
    </div>

    <div class="research-list">
      {#each research as item}
        <article class="research-card">
          <div class="card-top">
            <span class="year">{item.year}</span>
            <span class="status">{item.status}</span>
          </div>

          <h3>{item.title}</h3>

          <p class="venue">{item.venue}</p>

          {#if item.award}
            <p class="award">🥈 {item.award}</p>
          {/if}

          <!-- <div class="tags">
            {#each item.tags as tag}
              <span>{tag}</span>
            {/each}
          </div> -->

          <p class="desc">{item.desc}</p>

          <div class="links">
            {#each item.links as link}
              <a href={link.url} target="_blank" rel="noopener noreferrer">
                {link.label} ↗
              </a>
            {/each}
          </div>
        </article>
      {/each}
    </div>
  </section>
</FadeIn>

<style>
  .research-section {
    padding: 2.5rem 10rem 0 10rem;
    box-sizing: border-box;
    font-family: 'Satoshi', Arial, sans-serif;
  }

  .research-intro {
    max-width: 850px;
    margin: 0 auto 2.5rem auto;
    text-align: center;
  }

  .research-intro p {
    margin: 0;
    color: #333;
    font-size: 1.05rem;
    line-height: 1.7;
  }

  .research-list {
    display: flex;
    flex-direction: column;
    gap: 1.75rem;
  }

  .research-card {
    background: rgba(249, 249, 237, 0.88);
    border: 1.5px solid #b8c58a;
    border-radius: 22px;
    padding: 2rem;
    transition:
      transform 0.25s ease,
      box-shadow 0.25s ease,
      border-color 0.25s ease;
  }

  .research-card:hover {
    transform: translateY(-4px);
    border-color: #83943d;
    box-shadow: 0 12px 28px rgba(41, 71, 42, 0.12);
  }

  .card-top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 1rem;
    margin-bottom: 1rem;
  }

  .year {
    font-style: italic;
    color: #3e3e3e;
    font-size: 1rem;
  }

  .status {
    color: #29472a;
    background: #dfe8bd;
    border: 1.2px solid #83943d;
    border-radius: 999px;
    padding: 0.35rem 0.75rem;
    font-size: 0.82rem;
    font-weight: 700;
    white-space: nowrap;
  }

  h3 {
    margin: 0 0 0.55rem 0;
    color: #29472a;
    font-size: 1.35rem;
    line-height: 1.35;
    letter-spacing: -0.3px;
  }

  .venue {
    margin: 0 0 0.4rem 0;
    color: #555;
    font-size: 1rem;
    font-weight: 600;
  }

  .award {
    margin: 0.25rem 0 0.9rem 0;
    color: #6C7B3E;
    font-size: 0.95rem;
    font-weight: 700;
  }

  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.55rem;
    margin: 1rem 0;
  }

  .tags span {
    border: 1px solid #83943d;
    color: #29472a;
    background: rgba(255, 255, 255, 0.45);
    border-radius: 999px;
    padding: 0.35rem 0.7rem;
    font-size: 0.82rem;
    font-weight: 600;
  }

  .desc {
    margin: 0 0 1.4rem 0;
    color: #333;
    line-height: 1.65;
    font-size: 1rem;
  }

  .links {
    display: flex;
    gap: 0.85rem;
    flex-wrap: wrap;
  }

  .links a {
    display: inline-block;
    color: #29472a;
    border: 1.5px solid #29472a;
    border-radius: 999px;
    padding: 0.55rem 1rem;
    font-size: 0.92rem;
    font-weight: 700;
    text-decoration: none;
    transition:
      background 0.2s ease,
      color 0.2s ease,
      transform 0.2s ease;
  }

  .links a:hover {
    background: #29472a;
    color: #F9F9ED;
    transform: translateY(-2px);
  }

  @media (max-width: 900px) {
    .research-section {
      padding: 2.5rem 2rem 0 2rem;
    }

    .card-top {
      align-items: flex-start;
      flex-direction: column;
    }
  }

  @media (max-width: 500px) {
    .research-card {
      padding: 1.4rem;
    }

    h3 {
      font-size: 1.1rem;
    }

    .research-intro p,
    .desc {
      font-size: 0.95rem;
    }

    .status {
      white-space: normal;
    }
  }
</style>