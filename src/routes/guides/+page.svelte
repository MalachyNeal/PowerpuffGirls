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

{#each guides as guide}
  <div>
    <h3>{guide.title}</h3>
    <p>{guide.description}</p>

  </div>
  {/each}

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
</style>