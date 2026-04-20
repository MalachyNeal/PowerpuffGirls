<script>
    const entertainmentItems = [
        { id: 1, name: 'IMC Cinema' },
        { id: 2, name: 'The Dome Entertainment Centre' },
        { id: 3, name: 'Graiguecullen Swimming Pool' },
        { id: 4, name: 'The Foundry Nightclub' }
    ];

    const popularPlacesItems = [
        { id: 5, name: 'Brownshill Portal Dolmen' },
        { id: 6, name: 'Carlow County Museum' },
        { id: 7, name: 'Carlow Castle' },
        { id: 8, name: "Duckett's Grove" }
    ];

    const shoppingItems = [
        { id: 9, name: 'Carlow Shopping Centre' },
        { id: 10, name: 'Fairgreen Shopping Centre' },
        { id: 11, name: 'Penneys' },
        { id: 12, name: 'Haddens Centre' }
    ];

    let selectedCategory = '';
    let selectedActivity = '';
    let savedActivities = [];

    function getActivitiesForCategory() {
        if(selectedCategory === 'Entertainment') {
            return entertainmentItems;
        }

        if(selectedCategory === 'Popular Places') {
            return popularPlacesItems;
        }

        if(selectedCategory === 'Shopping') {
            return shoppingItems;
        }

        return [];
    }

    function handleCategoryChange() {
        selectedActivity = '';
    }

    function addActivity() {
        if (selectedCategory === '' || selectedActivity === '') {
            return;
        }

        let activityAlreadySaved = false;

        for (let i = 0; i < savedActivities.length; i++) {
            if (savedActivities[i].name === selectedActivity) {
                activityAlreadySaved = true;
            }
        }

        if(activityAlreadySaved === true) {
            return;
        }

        savedActivities.push({
            id: Date.now(),
            name: selectedActivity,
            category: selectedCategory
        });

        savedActivities = savedActivities;
        selectedCategory = '';
        selectedActivity = '';
    }
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
            {#each entertainmentItems.slice(0, 3) as item}
                <div class="activity-card">
                    <div class="image-placeholder"></div>
                    <p class="activity-name">{item.name}</p>
                    <button class="go-button" aria-label={'Go to ${item.name}'}>GO</button>
                </div>
            {/each}
        </div>

        <div class="mobile-card">
            <div class="activity-card">
                <div class="image-placeholder"></div>
                <p class="activity-name">{entertainmentItems[0].name}</p>
                <button class="go-button" aria-label={'Go to ${entertainmentItems[0].name}'}>GO</button>
            </div>
        </div>

        <button class="view-all-button">View All</button>
    </section>

    <section class="category-section">
        <h2>Popular Places</h2>

        <div class="card-grid desktop-cards">
            {#each popularPlacesItems.slice(0, 3) as item}
                <div class="activity-card">
                    <div class="image-placeholder"></div>
                    <p class="activity-name">{item.name}</p>
                    <button class="go-button" aria-label={'Go to ${item.name}'}>GO</button>
                </div>
            {/each}
        </div>

        <div class="mobile-card">
            <div class="activity-card">
                <div class="image-placeholder"></div>
                <p class="activity-name">{popularPlacesItems[0].name}</p>
                <button class="go-button" aria-label={'Go to ${popularPlacesItems[0].name}'}>GO</button>
            </div>
        </div>

        <button class="view-all-button">View All</button>
    </section>

    <section class="category-section">
        <h2>Shopping</h2>

        <div class="card-grid desktop-cards">
            {#each shoppingItems.slice(0, 3) as item}
                <div class="activity-card">
                    <div class="image-placeholder"></div>
                    <p class="activity-name">{item.name}</p>
                    <button class="go-button" aria-label={'Go to ${item.name}'}>GO</button>
                </div>
            {/each}
        </div>

        <div class="mobile-card">
            <div class="activity-card">
                <div class="image-placeholder"></div>
                <p class="activity-name">{shoppingItems[0].name}</p>
                <button class="go-button" aria-label={'Go to ${shoppingItems[0].name}'}>GO</button>
            </div>
        </div>

        <button class="view-all-button">View All</button>
    </section>

    <section class="saved-section">
        <h2>Saved Activities</h2>

        <div class="saved-form">
            <div class="field">
                <label for="category-select">Category</label>
                <select id="category-select" bind:value={selectedCategory} on:change={handleCategoryChange}>
                    <option value="">Select a category</option>
                    <option value="Entertainment">Entertainment</option>
                    <option value="Popular Places">Popular Places</option>
                    <option value="Shopping">Shopping</option>
                </select>
            </div>

            {#if selectedCategory !== ''}
                <div class="field">
                    <label for="activity-select">Activity</label>
                    <select id="activity-select" bind:value={selectedActivity}>
                        <option value="">Select an activity</option>
                        {#each getActivitiesForCategory() as activity}
                            <option value={activity.name}>{activity.name}</option>
                        {/each}
                    </select>
                </div>
            {/if}

            <button class="primary-button" on:click={addActivity}>Add to Saved List</button>
        </div>

        {#if savedActivities.length === 0}
            <p class="empty-message">No saved activities yet.</p>
        {:else}
            <div class="saved-list">
                {#each savedActivities as activity}
                    <div class="saved-item">
                        <p class="saved-category">{activity.category}</p>
                        <p class="saved-name">{activity.name}</p>
                    </div>
                {/each}
            </div>
        {/if}
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

    .saved-section {
        margin-top: var(--space-xl);
        padding-top: var(--space-sm);
    }

    h2 {
        font-size: var(--font-xl);
        margin-bottom: var(--space-md);
        text-align: center;
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
        text-align: center;
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

    .saved-form {
        display: flex;
        flex-direction: column;
        gap: var(--space-md);
        max-width: 500px;
        margin: 0 auto var(--space-lg);
    }

    .field {
        display: flex;
        flex-direction: column;
        gap: var(--space-xs);
    }

    .saved-list {
        display: flex;
        flex-direction: column;
        gap: var(--space-sm);
        max-width: 500px;
        margin: 0 auto;
    }

    .saved-item {
        background-color: var(--color-background);
        border: 1px solid var(--color-border);
        border-radius: var(--radius-md);
        padding: var(--space-md);
    }

    .saved-name {
        margin: 0;
    }

    .saved-category {
        margin: 0 0 var(--space-xs);
        font-weight: 600;
        color: var(--color-secondary);
    }

    .empty-message {
        text-align: center;
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