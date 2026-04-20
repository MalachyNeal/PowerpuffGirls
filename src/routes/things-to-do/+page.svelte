<script>
    const entertainmentItems = [
        { id: 1, name: 'Activity Name' },
        { id: 2, name: 'Activity Name' },
        { id: 3, name: 'Activity Name' }
    ];

    const popularPlacesItems = [
        { id: 4, name: 'Activity Name' },
        { id: 5, name: 'Activity Name' },
        { id: 6, name: 'Activity Name' }
    ];

    const shoppingItems = [
        { id: 7, name: 'Activity Name' },
        { id: 8, name: 'Activity Name' },
        { id: 9, name: 'Activity Name' }
    ];
</script>

<svelte:head>
    <title>Things to Do</title>
</svelte:head>

<div class="things-page">
    <div class="top-bar">
        <h1>Things to Do</h1>
    </div>

    <section class="category-section">
        <h2>Entertainment</h2>

        <div class="card-grid desktop-cards">
            {#each entertainmentItems as item}
                <div class="activity-card">
                    <div class="image-placeholder"></div>
                    <p class="activity-name">{item.name}</p>
                    <button class="go-button">GO</button>
                </div>
            {/each}
        </div>

        <div class="mobile-card">
            <div class="activity-card">
                <div class="image-placeholder"></div>
                <p class="activity-name">{entertainmentItems[0].name}</p>
                <button class="go-button">GO</button>
            </div>
        </div>

        <button class="view-all-button">View All</button>
    </section>

    <section class="category-section">
        <h2>Popular Places</h2>

        <div class="card-grid desktop-cards">
            {#each popularPlacesItems as item}
                <div class="activity-card">
                    <div class="image-placeholder"></div>
                    <p class="activity-name">{item.name}</p>
                    <button class="go-button">GO</button>
                </div>
            {/each}
        </div>

        <div class="mobile-card">
            <div class="activity-card">
                <div class="image-placeholder"></div>
                <p class="activity-name">{popularPlacesItems[0].name}</p>
                <button class="go-button">GO</button>
            </div>
        </div>

        <button class="view-all-button">View All</button>
    </section>

    <section class="category-section">
        <h2>Shopping</h2>

        <div class="card-grid desktop-cards">
            {#each shoppingItems as item}
                <div class="activity-card">
                    <div class="image-placeholder"></div>
                    <p class="activity-name">{item.name}</p>
                    <button class="go-button">GO</button>
                </div>
            {/each}
        </div>

        <div class="mobile-card">
            <div class="activity-card">
                <div class="image-placeholder"></div>
                <p class="activity-name">{shoppingItems[0].name}</p>
                <button class="go-button">GO</button>
            </div>
        </div>

        <button class="view-all-button">View All</button>
    </section>
</div>

<style>
    .things-page {
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

    .category-section {
        text-align: center;
        margin-bottom: var(--space-xl);
        padding-top: var(--space-xs);
    }

    h2 {
        font-size: var(--font-xl);
        margin-bottom: var(--space-md);
    }

    .card-grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: var(--space-xl);
        align-items: start;
    }

    .mobile-card {
        display: none;
    }

    .desktop-cards {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: var(--space-xl);
        align-items: start;
    }

    .activity-card {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .image-placeholder {
        width: 300px;
        max-width: 100%;
        height: 220px;
        background-color: var(--color-accent);
        border: 1px solid var(--color-border);
        margin-bottom: var(--space-sm);
    }

    .activity-name {
        margin: 0 0 var(--space-xs);
        font-size: var(--font-base);
    }

    .go-button {
        background: var(--color-primary);
        color: var(--text-contrast);
        padding: var(--space-xs) var(--space-md);
        border-radius: var(--radius-sm);
        font-size: var(--font-sm);
        font-weight: 600;
        border: none;
    }

    .go-button:hover,
    .go-button:focus {
        background: var(--color-secondary);
    }

    .view-all-button {
        background: var(--color-background);
        color: var(--color-text);
        border: 1px solid var(--color-accent);
        padding: var(--space-xs) var(--space-md);
        border-radius: var(--radius-sm);
        font-size: var(--font-sm);
        font-weight: 500;
        margin-top: var(--space-sm);
    }

    @media (max-width: 1024px) {
        .things-page {
            padding: var(--space-sm);
        }

        .desktop-cards {
            display: none;
        }

        .mobile-card {
            display: flex;
            justify-content: center;
        }

        .image-placeholder {
            width: 300px;
            max-width: 100%;
            height: 220px;
        }

        .activity-card {
            width: 100%;
            align-items: center;
        }
    }
</style>