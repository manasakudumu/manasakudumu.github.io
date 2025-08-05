<script>
    import FadeIn from '../components/FadeIn.svelte';
    import { slide } from 'svelte/transition';
    const experiences = [
      {
        date: "May 2025 – Present",
        org: "MIT Computer Science & Artificial Intelligence Laboratory | Mantis AI",
        role: "Software Engineer and Research Intern",
        img: "mitCSAIL.png",
        desc: "Developing an interactive AI-powered platform for large-scale geospatial and financial analysis. Leveraged OpenAI for semantic product-to-industry mapping and dynamic cluster-based visualization."
      },
      {
        date: "May 2024 – Present",
        org: "Wellesley College Accessibility Lab",
        role: "Undergraduate Research Assistant",
        img: "wells.png",
        desc: "Assisted Professor Gadiraju in Google-funded research on how users with disabilities use LLMs. Interviewed people with disabilities and maintained a comprehensive database of interactions and conducted diary studies to understand how they use generative AI chatbots, particularly Gemini. Used qualitative coding to categorize these use cases. Presented our paper at the ACM SIGACCESS Conference on Computers and Accessibility in St.Johns, Canada and won second place in the undergraduate category as part of their Student Research Competition."
      },
      {
        date: "Jul 2024 – Sep 2024",
        org: "MIT Teaching Systems Lab",
        role: "Undergraduate Summer Researcher",
        img: "mit.png",
        desc: "Analyzed qualitative interview data from teachers and students on their experiences with Generative AI tools in K-12 education. Utilized Atlas.ti to code and organize interview transcripts. Assisted in synthesizing key themes and insights from the first full academic year of widespread generative AI availability in schools. Contributed towards the TeachLab podcast by Prof. Justin Reich."
      },
      {
        date: "Apr 2025 – Present",
        org: "Hack @ Wellesley",
        role: "Treasury Lead",
        img: "whack.png",
        desc: "Lead the managing of the financial strategy for Wellesley’s annual hackathon, overseeing budgeting, tracking, and fund allocation to support seamless event execution. Help drive sponsorship outreach and fundraising campaigns, securing from industry partners and alumni to power innovative student experiences and support participation from 300+ attendees across New England"
      },
      {
        date: "Dec 2021 – Jun 2023",
        org: "Technovation – Team Noor",
        role: "Founder & CEO",
        img: "technovation.png",
        desc: "Led an all-girls team of three as the CEO. We developed a mobile app called 'Noor' using MIT App Inventor. Noor strives to promote education and inclusivity among visually impaired students by providing them with scribes, audiobooks, a platform to showcase their talents, a list of job opportunities that they might require in the future as well as conducting events/ forums. NGOs/ volunteers can make use of this app by volunteering as scribes and donating. Worked on the entrepreneurial part of the app as well which comprised of designing a business plan to bring the app to the market and filmed a pitch/ demo video presenting Noor's goals and functionalities."
      }
    ];
    let openStates = Array(experiences.length).fill(false);
</script>

<FadeIn>
  <section id="experience">
    {#each experiences as exp, i}
      <div class="exp-item" class:open={openStates[i]}>
        <div class="exp-summary" on:click={() => openStates[i] = !openStates[i]}>
          <span class="date">{exp.date}</span>
          <span class="org-role">
            <span class="org">{exp.org}</span>
            <span class="role">{exp.role}</span>
          </span>
        </div>
        {#if openStates[i]}
          <div class="exp-desc" in:slide={{ duration: 300 }} out:slide={{ duration: 300 }}>
            <img class="exp-logo" src={exp.img} alt="{exp.org} logo" />
            <p>{exp.desc}</p>
          </div>
        {/if}
      </div>
    {/each}
  </section>
</FadeIn>

<style>
  #experience {
    padding: 2.5rem 10rem 0 10rem;
    box-sizing: border-box;
    font-family: 'Satoshi', Arial, sans-serif;
  }
  .exp-item + .exp-item { margin-top: 2.5rem; }
  .exp-summary {
    display: grid;
    grid-template-columns: 180px 1fr 24px;
    align-items: center;
    cursor: pointer;
    padding: 0.75rem 0;
    position: relative;
  }
  .exp-summary::after {
    content: '›';
    justify-self: center;
    transform: rotate(90deg);
    transition: transform 0.3s ease;
    color: #555;
  }
  .exp-item.open .exp-summary::after {
    transform: rotate(-90deg);
  }
  .date {
    font-style: italic;
    color: #3e3e3e;
    font-size: 1rem;
  }
  .org-role {
    display: flex;
    flex-direction: column;
    gap: 0.1rem;
    color: #29472a;
    font-size: 1.1rem;
  }
  .org { font-weight: 700; }
  .role { font-weight: 500; color: #555; }
  .exp-desc {
    display: grid;
    grid-template-columns: 100px 1fr;
    gap: 1rem;
    padding: 0.5rem 0 1rem 180px;
    align-items: start;
  }
  .exp-logo {
    width: 100px;
    object-fit: contain;
    justify-self: start;
  }
  .exp-desc p {
    margin: 0;
    color: #333;
    line-height: 1.6;
    font-size: 1rem;
  }
  @media (max-width: 900px) {
    #experience {
      padding: 2.5rem 2rem 0 2rem;
    }
    .exp-summary {
      grid-template-columns: 1fr; 
      gap: 0.5rem;
    }
    .exp-desc {
      grid-template-columns: 1fr; 
      padding: 1rem 0 1rem 0;
    }
    .exp-logo {
      width: 80px;
      margin-bottom: 0.5rem;
    }
  }
  @media (max-width: 500px) {
    .org-role {
      font-size: 1rem;
    }
    .date {
      font-size: 0.9rem;
    }
    .exp-desc p {
      font-size: 0.95rem;
    }
    .exp-logo {
      width: 70px;
    }
  }
</style>