
<script>
import { base } from '$app/paths';

let guides = [
        {
            title: "Altamont Gardens",
            description: "Beautiful gardens with revers and walking paths.",
            link:"https://www.altamontgarden.com",
            image:`${base}/images/Guides_Page/altamon_garden.jpg`
        },
        {
            title: "Brownshill Dolmen",
            description: "One of the largest dolmens in Ireland.",
            link:"https://heritageireland.ie/unguided-sites/brownshill-portal-dolmen/",
            image:`${base}/images/Guides_Page/brownshill_dolmen.jpg`
        
          },
        {
            title: "Carlow Castle",
            description: "A historic castle in Carlow town",
            link: "https://heritageireland.ie/unguided-sites/carlow-castle/",
            image:`${base}/images/Guides_Page/carlow_castle.jpg`
        },
        
    ];
    //search
  let search = '';

  /** @type {{title: string, description: string, link: string, image: string}[]} */
  let savedGuides = [];
  

 
  $: filteredGuides = guides.filter((guide) =>
    guide.title.toLowerCase().includes(search.toLowerCase())
  );

  
  // @ts-ignore
  function saveGuide(guide) {
    if (!savedGuides.find((item) => item.title === guide.title)) {
      savedGuides = [...savedGuides, guide];
    }
  }

  
  function removeGuide(/**@type {string}*/title) {
    savedGuides = savedGuides.filter((guide) => guide.title !== title);
  }
</script>

<h1>
    Travel Guides
</h1>
<p>Find travel ideas and explore different destinations easily.</p>

<input
  class="search"
  bind:value={search}
  placeholder="Search guides..."
  aria-label="Search travel guides"
/>

<div class="guides">
{#each filteredGuides as guide}
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
      <button class="btn save-btn" on:click={() => saveGuide(guide)}>
        Save Guide
      </button>
  </div>
  {/each}
</div>
        <h2>Saved Guides</h2>

{#if savedGuides.length === 0}
  <p>No saved guides yet.</p>
{:else}
  <div class="saved-list">
    {#each savedGuides as guide}
      <div class="saved-item">
        <span>{guide.title}</span>

        <button class="remove-btn" on:click={() => removeGuide(guide.title)}>
          Remove
        </button>
      </div>
   {/each}
  </div>
{/if}

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
   .search {
    width: 100%;
    max-width: 400px;
    padding: 10px;
    margin: 15px 0;
    border: 1px solid #ccc;
    border-radius: 8px;
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
  .btn:hover {
    background: #1f5c24;
  }
  .save-btn {
    margin-left: 8px;
    background: #4f6f8f;
  }

  .save-btn:hover {
    background: #39566f;
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
  
  .saved-list {
    margin-top: 15px;
    display: grid;
    gap: 10px;
  }

  .saved-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: white;
    padding: 12px;
    border-radius: 8px;
    box-shadow: 0 2px 6px rgba(0,0,0,0.1);
  }

  .remove-btn {
    background: #b33a3a;
    color: white;
    border: none;
    padding: 7px 12px;
    border-radius: 6px;
    cursor: pointer;
  }

  .remove-btn:hover {
    background: #8f2d2d;
  }
</style>

