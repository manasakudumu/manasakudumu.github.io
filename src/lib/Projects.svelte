<script>
	let projects = [
		{
			title: 'Interactive Foreclosure Visualizer',
			image: '/foreclosure.png',
			description: 'Story-driven Svelte + D3.js + Mapbox app visualizing foreclosure trends in Boston across time and neighborhoods.',
			link: 'https://manasakudumu.github.io/cs-portfolio/' 
		},
		{
			title: 'Accessible Education Platform – Noor',
			image: '/noor.png',
			description: 'Mobile app for visually impaired students with audiobooks, talent showcases, and job listings. 1st place at Smart India Hackathon.',
			link: 'https://manasakudumu.github.io/cs-portfolio/' 
		},
		{
			title: 'Bike Watching',
			image: '/bikewatching.png',
			description: 'Interactive map of Boston bike traffic with dynamic filters and animated flows using Svelte, D3.js, and Mapbox.',
			link: 'https://manasakudumu.github.io/cs-portfolio/'
		}
	];
</script>


<div class="gallery">
    {#each projects as project}
    <div class="proj">
        <a  href="{project.link}" target="_blank" rel="noopener"><img src="{project.image}" alt="{project.title}"></a>
        <h3>{project.title}</h3>
        <p>{project.description}</p>
    </div>
    {/each}
</div>

<style>
    .gallery{
        display:grid;
        grid-template-columns: repeat(3, 1fr);
        gap:2em;
        margin-top:4em;
    }

    @media (max-width: 900px) {
        .gallery {
            grid-template-columns: repeat(2, 1fr);
        }
    }
    @media (max-width: 600px) {
        .gallery {
            grid-template-columns: 1fr;
        }
    }

    .proj{
        border-radius: 20px;
        box-shadow:gray;
        overflow:hidden;
        padding:2em;
    }

    .proj img{
        width:100%;
        display:block;
        object-fit: cover;
        height:180px;
        overflow: hidden;
        object-fit: contain;
        aspect-ratio: 1/1;
        
    }
</style>