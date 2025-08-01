<script>
    import FadeIn from '../components/FadeIn.svelte';
	let projects = [
		{
			title: 'Interactive Foreclosure Visualizer',
			image: 'foreclosure.png',
			description: 'Story-driven Svelte + D3.js + Mapbox app visualizing foreclosure trends in Boston across time and neighborhoods.',
            technologies: ["Svelte", "D3.js", "Mapbox"],
			link: 'https://hannahchiou.github.io/hjc-project/' 
		},
		{
			title: 'Accessible Education Platform – Noor',
			image: 'noor.png',
			description: 'Mobile app for visually impaired students with audiobooks, talent showcases, and job listings. 1st place at Smart India Hackathon.',
            technologies: ["MIT App Inventor"],
			link: 'https://www.youtube.com/watch?v=mkOmThaUvvg' 
		},
		{
			title: 'Bike Watching',
			image: 'bikewatching.png',
			description: 'Interactive map of Boston bike traffic with dynamic filters and animated flows using Svelte, D3.js, and Mapbox.',
            technologies: ["Svelte", "D3.js", "Mapbox"],
			link: 'https://manasakudumu.github.io/bikingviz1/'
		}
	];
</script>

<FadeIn>
<section id="projects" class="projects-section">
	<div class="projects-grid">
		{#each projects as project}
			<div class="project-card">
				<a href={project.link} target="_blank" rel="noopener noreferrer">
					<img src={project.image} alt={project.title} />
				</a>
				<h3>{project.title}</h3>
				<p>{project.description}</p>
                <div class="tech-tags">
                    {#each project.technologies as tech}
                      <span class="tech-box">{tech}</span>
                    {/each}
                  </div>                  
			</div>
		{/each}
	</div>
</section>
</FadeIn>

<style>
.projects-section {
	padding: 5rem 2rem;
    max-width: 1300px;
    margin: 0 auto;
    
}

.projects-grid {
    display: grid;
	grid-template-columns: repeat(2, 1fr);
	gap: 2.5rem 2rem;
	max-width: 900px;
	margin: 0 auto;
	place-items: center; 
}

.project-card {
	border-radius: 16px;
	border: 1px solid #c4c4c4;
	padding: 2rem;
	box-shadow: 0 4px 12px rgba(0, 0, 0, 0.06);
	transition: transform 0.2s ease, border-color 0.2s ease;
	font-family: 'Satoshi', Arial, sans-serif;
	text-align: left;
    height: 420px;
}

.project-card:hover {
	transform: scale(1.025);
	border-color: #386641;
}

.project-card img {
	width: 100%;
	height: 200px;
	object-fit: cover;
	border-radius: 8px;
	margin-bottom: 1rem;
}

.project-card h3 {
	font-size: 1.3rem;
	color: #2e4322;
	margin: 0.8rem 0 0.5rem 0;
}

.project-card p {
	color: #444;
	font-size: 1rem;
	line-height: 1.5;
}

.tech-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-top: 1rem;
}

.tech-box {
  border: 2px solid #386641;
  color: black;
  padding: 0.3rem 0.75rem;
  border-radius: 25px;
  font-size: 0.85rem;
  font-weight: 600;
  font-family: 'Helvetica Neue', sans-serif;
  background-color: transparent;
  transition: background-color 0.2s ease;
}

@media (max-width: 500px) {
	.project-card {
		grid-template-columns: 1fr;
	}
}
</style>
