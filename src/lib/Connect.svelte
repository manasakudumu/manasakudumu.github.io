<section class="connect-band">
    <div class="connect-content">
        <h2>Let's connect!</h2>
      <p class="connect-desc">Let's talk projects, collaborations, or shared interests</p>
      <div class="connect-actions">
        <a href="mailto:your@email.com" class="green-outline-btn">Email</a>
        <a href="https://www.linkedin.com/in/manasa-kudumu-098670215/" target="_blank" class="green-outline-btn">LinkedIn</a>
      </div>      
    </div>
</section>
  

<style>
    .connect-band {
    width: 100vw;
    min-height: 320px;             
    display: flex;
    align-items: center;           
    justify-content: flex-start; 
    padding-left: 7vw;             
    padding-right: 2vw;
    margin: 0 calc(-50vw + 50%);   
    }

    .connect-content {
    max-width: 480px;
    width: 100%;
    text-align: left;
    }


    .connect-desc {
    font-size: 1.19rem;
    color: #293c32;
    margin-bottom: 1.5em;
    line-height: 1.55;
    }

    .connect-actions {
    display: flex;
    gap: 1.2em;
    margin-top: 2.2em;
    }

    .green-outline-btn {
    display: inline-block;
    font-family: inherit;
    font-size: 0.8em;
    font-weight: 600;
    letter-spacing: 0.16em;
    text-transform: uppercase;
    padding: 0.5em 1.5em;
    color: #6C7B3E;                 
    border: 2px solid #6C7B3E;
    background: transparent;
    border-radius: 0.7em;
    cursor: pointer;
    box-shadow: 0 2px 10px rgba(108, 123, 62, 0.05);
    transition: 
        background 0.18s, 
        color 0.18s, 
        border-color 0.18s,
        box-shadow 0.18s;
    text-decoration: none;
    }

    .green-outline-btn:hover, 
    .green-outline-btn:focus {
    background: #f6f9ed;
    color: #405014;
    border-color: #405014;
    box-shadow: 0 4px 18px rgba(108, 123, 62, 0.15);
    }


    @media (max-width: 800px) {
    .connect-band {
        min-height: 220px;
        padding-left: 5vw;
        padding-right: 5vw;
    }
    }

    @media (max-width: 600px) {
    .connect-band {
        min-height: 150px;
        padding-left: 3vw;
        padding-right: 3vw;
        justify-content: center;
    }
    .connect-content {
        max-width: 98vw;
        text-align: center;
    }
    }

</style>