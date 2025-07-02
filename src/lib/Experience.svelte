<script>
    let experiences = [
        {
            title: "Intern",
            organization: "Mantis AI",
            date: "June 2025",
            description: "Worked on AI product research.",
            logo: "/project1.png"
        },
        {
            title: "Research Assistant",
            organization: "Wellesley College",
            date: "May 2024 - Present",
            description: "Research on LLMs and accessibility.",
            logo: "/project1.png"
        },
        {
            title: "Treasury Lead",
            organization: "WHACK",
            date: "April 2025 - Present",
            description: "Hackathon financial management.",
            logo: "/project1.png"
        },
        {
            title: "Software Engineer Intern",
            organization: "Technovation",
            date: "Dec 2021 - Jun 2023",
            description: "Built inclusive learning tools.",
            logo: "/project1.png"
        }
    ];
</script>

<div class="timeline">
    {#each experiences as exp, i}
    <div class="timeline-row">
        <!-- Logo & vertical line -->
        <div class="timeline-center">
            {#if i !== 0}
              <span class="line top"></span>
            {/if}
            <div class="timeline-logo">
                <img src={exp.logo} alt={exp.organization} />
            </div>
            {#if i !== experiences.length - 1}
              <span class="line bottom"></span>
            {/if}
        </div>
        <!-- Experience Card -->
        <div class="timeline-card">
            <h3>{exp.title}</h3>
            <div class="org-date">
                <span class="org">{exp.organization}</span>
                <span class="date">{exp.date}</span>
            </div>
            <p>{exp.description}</p>
        </div>
    </div>
    {/each}
</div>

<style>
.timeline {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    width: 100%;
    max-width: 900px;
    margin: 0 auto;
}

.timeline-row {
    display: flex;
    flex-direction: row;
    align-items: center;
    min-height: 120px;
    width: 100%;
    margin-bottom: 1.5em;
}

.timeline-center {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 60px;
    position: relative;
    min-height: 100px;
}

.line {
    width: 4px;
    background: hsl(120, 19%, 44%);
    display: block;
}

.line.top {
    height: 50%;
}

.line.bottom {
    height: 50%;
}

.timeline-logo {
    z-index: 1;
    background: #edf0e4;
    padding: 4px;
    border-radius: 50%;
    margin: -2px 0;
}

.timeline-logo img {
    width: 40px;
    height: 40px;
    object-fit: cover;
    border-radius: 50%;
    display: block;
    border: 2px solid #b9c89c;
}

.timeline-card {
    text-align: left;
    margin-left: 2em;
    padding: 1em 2em;
    background: none;
}

.timeline-card h3 {
    margin: 0 0 0.2em 0;
    color: #84953d;
    font-family: 'Satoshi', Arial, sans-serif;
    font-weight: 700;
}

.org-date {
    font-size: 1.06em;
    color: #292929;
    margin-bottom: 0.3em;
}
.org {
    font-weight: 600;
    margin-right: 0.6em;
}
.date {
    color: #878787;
    font-size: 0.99em;
}
.timeline-card p {
    margin: 0.3em 0 0 0;
    color: #252525;
    font-size: 1em;
}

@media (max-width: 650px) {
    .timeline-row {
        flex-direction: column;
        align-items: flex-start;
    }
    .timeline-card {
        margin-left: 0;
        margin-top: 0.8em;
        padding: 1em;
    }
    .timeline-center {
        width: 40px;
    }
}
</style>
