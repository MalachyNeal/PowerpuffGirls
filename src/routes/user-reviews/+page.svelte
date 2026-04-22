<script>

    const ShopReviews = [
        {id: 1, name: "John Doe", text: "Wow, this is so very amazing, just fantastic looking at these shops."},
        {id: 2, name: "Joe Don", text: "Wow, I hate this, I utterly hate this, and you should hate this too"},
        {id: 3, name: "Jill Hillbert", text: "My wife left me"},
    ];

    const FoodReviews = [
        {id: 1, name: "John Doe", text: "Wow, this is so very amazing, just fantastic looking at these shops."},
        {id: 2, name: "Joe Don", text: "Wow, I hate this, I utterly hate this, and you should hate this too"},
        {id: 3, name: "Jill Hillbert", text: "My wife left me"},
    ];

    const AccomadationReviews = [
        {id: 1, name: "John Doe", text: "Wow, this is so very amazing, just fantastic looking at these shops."},
        {id: 2, name: "Joe Don", text: "Wow, I hate this, I utterly hate this, and you should hate this too"},
        {id: 3, name: "Jill Hillbert", text: "My wife left me"},
    ];
</script>

<svelte:head>
    <title>User Reviews</title>
</svelte:head>

<div class="users-page">
    <div class="top-bar">
        <h1>User Reviews</h1>
    </div>

    <section class="review-section">
        <h2>Shop Reviews</h2>

        <div class="mobile">
            <div class="grid">
                
            </div>
        </div>

        <div class="desktop">
            {#each ShopReviews.slice(0,3) as item}
                <div class="grid">
                    <p class="reviewer">{item.name}</p>
                    <p class="review">{item.text}</p>
                </div>
            {/each}
        </div>
    </section>

    <section class="review-section">
        <h2>Food Reviews</h2>

        <div class = "mobile">

        </div>

        <div class = "desktop">
            {#each FoodReviews.slice(0,3) as item}
                <div class="grid">
                    <p class="reviewer">{item.name}</p>
                    <p class="review">{item.text}</p>
                </div>
            {/each}
        </div>
    </section>

    <section class="review-section">
        <h2>Accomadation Reviews</h2>

        <div class ="mobile">

        </div>

        <div class ="desktop">
            {#each AccomadationReviews.slice(0,3) as item}
                <div class="grid">
                    <p class="reviewer">{item.name}</p>
                    <p class="review">{item.text}</p>
                </div>
            {/each}
        </div>
    </section>

    <section class="write-section">
        <h2>Write a Review</h2>

        <div>

        </div>
    </section>
</div>


<style>
    .users-page {
        max-width: 1600px;
        margin: 0 auto;
        padding: var(--space-sm) var(--space-lg) var(--space-xl);
    }

    .top-bar {
        text-align: center;
        margin-bottom: var(--space-sm);
        padding-bottom: var(--space-sm);
        border-bottom: 1px solid var(--color-border);
    }

    h1 {
        font-size: var(--font-xxl);
        margin: 0;
    }

    .review-section {
        text-align: center;
        margin-bottom: var(--space-xl);
        padding-top: var(--space-xs);
    }

    .write-section {
        text-align: center;
        margin-bottom: var(--space-xl);
        padding-top: var(--space-xs);
    }

    .grid {
        border: 1px solid;
    }

    .mobile {
        display: none;
    }

    .desktop {
        display: grid;
    }

    .reviewer {
        text-align: left;
    }

    .review {
        text-align: left;
    }

    @media (max-width: 1024){
        .mobile {
            display: none;
        }

        .desktop {
            display: grid;
        }
    }
</style>