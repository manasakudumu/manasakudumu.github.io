<script>
    import FadeIn from './FadeIn.svelte';
	let projects = [
		{
			title: 'Interactive Foreclosure Visualizer',
			image: 'foreclosure.png',
			description: 'Story-driven visualizations that analyze how housing insecurity and foreclosure disproportionately affect certain communities in Boston and what were the driving forces that led to their foreclosure.',
            technologies: ["Svelte", "D3.js", "Mapbox"],
			link: 'https://hannahchiou.github.io/hjc-project/' 
		},
		{
			title: 'Seam Carver Image Resizer',
			image: 'seamcarver5.png', 
			description: 'Employed dynamic programming to create an image resizing program that could reduce the width and height of a given image with minimal data/feature loss.',
			technologies: ["Java", "Flask", "Pillow"],
			link: 'https://github.com/manasakudumu/Seam-Carver'
		},
		{
			title: 'Trading Bot Backtester',
			image: 'trade.png',
			description: 'Simulated algorithmic stock trading using technical indicators like the SMA, EMA, and RSI. It allows for backtesting of strategies on real historical stock data using the Alpha Vantage API and evaluates performance using financial metrics.',
			technologies: ["Python", "Pandas", "Matplotlib", "requests"],
			link: 'https://github.com/manasakudumu/trading-bot'
		},
		{
			title: 'Shell',
			image: 'shell.png',
			description: 'Built a custom Unix shell in C supporting command parsing, piping, I/O redirection, background jobs, and signal handling. Implemented built-in commands like cd, jobs, fg, and bg with job control via a linked list.',
			technologies: ["C"],
			link: 'https://github.com/manasakudumu/custom-shell'
		},
		{
			title: 'Hollywood Gender Bias Graph',
			image: 'bechdel.png',
			description: 'Developed a bipartite graph of actors and movies from real-world Hollywood data to analyze gender representation using the Bechdel Test (asks whether a movie features at least two named women who talk to each other about something other than a man).',
			technologies: ["Java", "Graphs", "yEd", "OOP"],
			link: 'https://github.com/manasakudumu/Bechdel-Graph'
		},
		{
			title: 'Bike Watching',
			image: 'bikewatching.png',
			description: 'Built an immersive, interactive map of BlueBike traffic in Boston. The visualization supports time-of-day filtering, animated demand indicators, and isochrone overlays to explore biking accessibility across neighborhoods.',
			technologies: ["Svelte", "D3.js", "Mapbox"],
			link: 'https://manasakudumu.github.io/bikingviz1/'
		},
		{
			title: 'Noor: Accessible Education Platform',
			image: 'noor.png',
			description: 'Mobile app that strives to promote education and inclusivity among visually impaired students by connecting them with scribes, audiobooks, a platform to showcase their talents, and a list of job opportunities- 1st place at Smart India Hackathon.',
            technologies: ["MIT App Inventor"],
			link: 'https://www.youtube.com/watch?v=mkOmThaUvvg' 
		},
		{
			title: 'Bubble : Food Social Media App',
			image: 'bubble.png',
			description: 'Social media inspired app where Wellesley students can log meals, reflect on mood, and share food reviews. Integrated with Wellesley Fresh API to fetch real dining hall menus by day.',
			technologies: ["Streamlit", "Python", "SQLite", "Cloudinary"],
			link: 'https://bubble.streamlit.app'
		},
	];
</script>
<FadeIn>
	<section id="projects" class="p-section">
	  <div class="p-grid">
		{#each projects as project}
		  <div class="p-card">
			<a href={project.link} target="_blank" rel="noopener noreferrer">
			  <img src={project.image} alt={project.title}/>
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
	.p-section {
	  padding: 5rem 10rem;      
	  box-sizing: border-box;
	  font-family: 'Satoshi', Arial, sans-serif;
	}
	.p-grid {
	  display: grid;
	  grid-template-columns: repeat(2, 1fr);
	  gap: 2.5rem 2rem;
	}
	.p-card {
	  width: 100%;
	  max-width: 470px;
	  border-radius: 16px;
	  border: 1px solid #c4c4c4;
	  background: #F9F9ED;
	  padding: 2rem;
	  transition: transform 0.2s ease, border-color 0.2s ease;
	}
	.p-card:hover {
	  transform: scale(1.025);
	  border-color: #386641;
	}
	.p-card img {
	  width: 100%;
	  height: 200px;
	  object-fit: cover;
	  border-radius: 8px;
	  margin-bottom: 1rem;
	}
	.p-card h3 {
	  font-size: 1.3rem;
	  color: #2e4322;
	  margin: 0.8rem 0 0.5rem;
	  text-align: center;
	}
	.p-card p {
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
	  padding: 0.3rem 0.75rem;
	  border-radius: 25px;
	  font-size: 0.85rem;
	  font-weight: 600;
	  background: transparent;
	}
	@media (max-width: 960px) {
		.p-section {
			padding: 3rem 3rem;
		}
		.p-grid {
			grid-template-columns: 1fr; 
			justify-items: center;
		}
		.p-card {
			max-width: 90%;
		}
	}
	@media (max-width: 500px) {
		.p-section {
			padding: 2rem 1.2rem;
		}
		.p-card {
			padding: 1.4rem;
		}
		.p-card img {
			height: 180px;
		}
		.p-card h3 {
			font-size: 1.15rem;
		}
		.p-card p {
			font-size: 0.95rem;
		}
		.tech-box {
			font-size: 0.78rem;
			padding: 0.25rem 0.6rem;
		}
	}
</style>