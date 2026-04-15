<script>
let guides = [
        {
            title: "Altamont Gardens",
            description: "Beautiful gardens with revers and walking paths."
        },
        {
            title: "Brownshill Dolmen",
            description: "One of the largest dolmens in Ireland."
        },
        {
            title: "Carlow Castle",
            description: "A historic castle in Carlow town"
        }
        
    ];
</script>
<h1>
    Travel Guides
</h1>
<p>Find travel ideas and explore different destinations easily.</p>

<div class="guides">
{#each guides as guide}
  <div class="card">
    <h3>{guide.title}</h3>
    <p>{guide.description}</p>

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
  }

  .card h3 {
    margin-bottom: 10px;
  }
</style>