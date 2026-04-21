<svelte:head>
    <title>User Reviews</title>
</svelte:head>

<div class="users-page">
    <div class="top-bar">
        <h1>User Reviews</h1>
    </div>

    <section class="review-section">
        <h2>Shop Reviews</h2>

        <div>

        </div>
    </section>

    <section class="review-section">
        <h2>Food Reviews</h2>

        <div>

        </div>
    </section>

    <section class="review-section">
        <h2>Accomadation Reviews</h2>

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
</style>