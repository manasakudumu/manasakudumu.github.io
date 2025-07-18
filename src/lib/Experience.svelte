<script>
    import { fly } from 'svelte/transition';

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
            description: "- Assisted Professor Gadiraju in Google-funded research on how users with disabilities use LLMs. Interviewed people with disabilities and maintained a comprehensive database of interactions and conducted diary studies to understand how they use generative AI chatbots, particularly Gemini. Used qualitative coding to categorize these use cases. Presented our paper at the ACM SIGACCESS Conference on Computers and Accessibility in St.Johns, Canada and won second place in the undergraduate category as part of their Student Research Competition.- Assisted Professor Gadiraju in Google-funded research on how users with disabilities use LLMs - Interviewed people with disabilities and maintained a comprehensive database of interactions and conducted diary studies to understand how they use generative AI chatbots, particularly Gemini - Used qualitative coding to categorize these use cases. - Presented our paper at the ACM SIGACCESS Conference on Computers and Accessibility in St.Johns, Canada and won second place in the undergraduate category as part of their Student Research Competition.", 
            logo: "/project1.png" },
        { 
            title: "Treasury Lead", 
            organization: "WHACK", 
            date: "April 2025 - Present", 
            description: "Hackathon financial management.", 
            logo: "/project1.png" },
        { 
            title: "Software Engineer Intern", 
            organization: "Technovation", 
            date: "Dec 2021 - Jun 2023", 
            description: "Built inclusive learning tools.", 
            logo: "/project1.png" }
    ];

    let visible = Array(experiences.length).fill(false);

    function onEnter(index) {
        visible = visible.slice();
        visible[index] = true;
    }

    function observe(node, index) {
        const observer = new IntersectionObserver(
            ([entry]) => {
                if (entry.isIntersecting) {
                    onEnter(index);
                    observer.unobserve(node);
                }
            },
            { threshold: 0.12 }
        );
        observer.observe(node);
        return {
            destroy() {
                observer.disconnect();
            }
        };
    }
</script>

<div class="experience-section">
    {#each experiences as exp, i}
        <div class="experience-trigger" use:observe={i}></div>
        {#if visible[i]}
            <div
                class="exp-row"
                in:fly={{ y: 60, duration: 550, delay: 0, opacity: 0 }}
            >
                <div class="exp-left">
                    <h3>{exp.title}</h3>
                    <span class="org">{exp.organization}</span>
                    <span class="date">{exp.date}</span>
                </div>
                <div class="exp-right">
                    <p>{exp.description}</p>
                </div>
            </div>
        {/if}
    {/each}
</div>


<style>
.experience-section {
    width: 100%;
    max-width: 900px;
    margin: 0 auto;
    padding: 2em 0;
}

.exp-row {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    justify-content: space-between;
    background: #f8faef; /* pale green background, adjust as needed */
    margin-bottom: 2em;
    border-radius: 1.5em;
    padding: 2em;
    transition: box-shadow 0.2s;
}


.exp-left {
    min-width: 230px;
    max-width: 290px;
    flex: 1 0 230px;
    padding-right: 2.5em;
}

.exp-left h3 {
    margin: 0 0 0.3em 0;
    color: #7e9331;
    font-size: 1.4em;
    font-family: 'Satoshi', Arial, sans-serif;
    font-weight: 700;
}

.exp-left .org {
    display: block;
    font-weight: 600;
    color: #56701d;
    margin-bottom: 0.2em;
    font-size: 1.09em;
}

.exp-left .date {
    display: block;
    color: #97a262;
    font-size: 1em;
    margin-top: 0.2em;
}

.exp-right {
    flex: 2 1 400px;
    color: #222;
    font-size: 1.08em;
    line-height: 1.6;
    padding-left: 0.5em;
}

.experience-trigger {
  width: 100%;
  height: 80px;  
}

@media (max-width: 700px) {
    .exp-row {
        flex-direction: column;
        padding: 1.2em;
    }
    .exp-left {
        padding-right: 0;
        margin-bottom: 0.7em;
        max-width: 100%;
    }
    .exp-right {
        padding-left: 0;
    }
}

</style>
