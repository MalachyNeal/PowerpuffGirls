<script>
let guides = [
        {
            title: "Altamont Gardens",
            description: "Beautiful gardens with revers and walking paths.",
            link:"https://www.altamontgarden.com",
            image:"/images/Guides_Page/altamon_garden.jpg"
        },
        {
            title: "Brownshill Dolmen",
            description: "One of the largest dolmens in Ireland.",
            link:"https://heritageireland.ie/unguided-sites/brownshill-portal-dolmen/",
            image:"/images/Guides_Page/brownshill_dolmen.jpg"
        
          },
        {
            title: "Carlow Castle",
            description: "A historic castle in Carlow town",
            link: "https://heritageireland.ie/unguided-sites/carlow-castle/",
            image:"/images/Guides_Page/carlow_castle.jpg"
        },
        
    ];
</script>
<h1>
    Travel Guides
</h1>
<p>Find travel ideas and explore different destinations easily.</p>

<div class="guides">
{#each guides as guide}
  <div class="card">
  <div class ="image-box">
    <img src={guide.image}
    alt={guide.title}/>
  </div>
    <h3>{guide.title}</h3>
    <p>{guide.description}</p>

    <a href={guide.link} target="_blank"
    class="btn">
     View Guide
      </a>

  </div>
  {/each}
  </div>

<style>
  h1 {
    font-size: 28px;
    margin-bottom: 10px;
  }

  p {
    font-size: 16px;
    color: #444;
    margin-bottom: 20px;
  }
  .guides {
      display: grid;
      grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
      gap: 20px;
      margin-top: 20px;
  }

  .card {
    background: white;
    padding: 15px;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    transition: transform 0.2s ease;
  }

  .card:hover {
    transform: scale(1.03);
    transition: 0.2s;
  }

  .card h3 {
    margin-bottom: 10px;
  }

  .btn {
    display: inline-block;
    background: #2e7d32;
    color:white;
    border:none;
    padding: 8px 14px;
    border-radius: 6px;
    text-decoration: none;
    cursor: pointer;
    margin-top: 10px;
  }
  button:hover {
    background: #1f5c24;
  }
  .image-box {
    height:160px;
    overflow: hidden;
    border-radius: 8px;
    margin-bottom: 12px;
  }
  .image-box img{
    width: 100%;
    height:100%;
    object-fit: cover;
  }
</style>