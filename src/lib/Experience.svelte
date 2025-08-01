<script>
    import FadeIn from '../components/FadeIn.svelte';
    const experiences = [
      {
        date: "May 2025 – Present",
        org: "MIT CSAIL – Mantis AI",
        role: "Software Engineer Intern",
        desc: "Developing an interactive AI-powered platform for large-scale geospatial and financial analysis. Leveraged OpenAI for semantic product-to-industry mapping and dynamic cluster-based visualization."
      },
      {
        date: "May 2024 – Present",
        org: "Wellesley College – Accessibility Lab",
        role: "Undergraduate Research Assistant",
        desc: "Interviewed 30+ disabled users and conducted qualitative coding to study how people use LLMs like Gemini. Co-authored an award-winning paper at ACM SIGACCESS 2024 on inclusive chatbot interactions."
      },
      {
        date: "Jul 2024 – Sep 2024",
        org: "MIT Teaching Systems Lab",
        role: "Undergraduate Summer Researcher",
        desc: "Analyzed interview data from K–12 educators using GenAI in classrooms. Conducted thematic coding in Atlas.ti, and contributed to the TeachLab podcast on AI in education led by Prof. Justin Reich."
      },
      {
        date: "Apr 2025 – Present",
        org: "Hack @ Wellesley",
        role: "Treasury Lead",
        desc: "Led budgeting, fund allocation, and sponsorship outreach for Wellesley’s annual hackathon, managing finances and securing industry partners for 200+ attendees."
      },
      {
        date: "Dec 2021 – Jun 2023",
        org: "Technovation – Team Noor",
        role: "Founder & CEO",
        desc: "Built Noor, an app for blind students with audiobooks and job boards. Led product, design, and fundraising. 1st place winner at Smart India Hackathon and Technovation Girls semifinalist."
      }
    ];
  </script>
  
  <FadeIn>
  <section id="experience">
    <div class="timeline">
      {#each experiences as exp}
        <div class="experience-item">
          <div class="date">{exp.date}</div>
          <div class="details">
            <p class="title">
              <span class="org">{exp.org}</span>
              <span class="dot"> • </span>
              <span class="role">{exp.role}</span>
            </p>
            <p class="desc">{exp.desc}</p>
          </div>
        </div>
      {/each}
    </div>
  </section>
</FadeIn>
  
  

<style>
#experience {
  padding: 4rem 2rem;
  font-family: 'Satoshi', Arial, sans-serif;
}

.timeline {
  display: grid;
  grid-template-columns: 180px 1fr; /* Left: date, Right: details */
  row-gap: 3rem;
  max-width: 900px;
  margin: 0 auto;
}

.experience-item {
  display: contents; /* Allows grid children to align */
}

.date {
  font-size: 1.1rem;
  font-style: italic;
  color: #3e3e3e;
  padding-top: 0.25rem;
  margin-top: 0.9rem;
}

.details {
  display: flex;
  flex-direction: column;
}

.title {
  font-size: 1.1rem;
  font-weight: 600;
  color: #29472a;
}

.org {
  font-weight: 700;
}

.role {
  font-weight: normal;
  color: #555;
}

.dot {
  margin: 0 0.3rem;
  color: #999;
}

.desc {
  margin-top: 0.3rem;
  font-size: 1rem;
  line-height: 1.6;
  color: #333;
}

  
</style>
