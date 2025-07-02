<script>
    let projects;
    projects=[
        {
            title:'Project title',
            image:'/project1.png',
            description: 'A short description of what this project is about.',
            link: 'https://hannahchiou.github.io/hjc-project/'
        },
        {
            title:'Project title',
            image:'/project1.png',
            description: 'A short description of what this project is about.',
            link: 'https://hannahchiou.github.io/hjc-project/'
        },
        {
            title:'Project title',
            image:'/project1.png',
            description: 'A short description of what this project is about.',
            link: 'https://hannahchiou.github.io/hjc-project/'
        },
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