<svelte:head>
    <title>Carlow Tourism</title>
</svelte:head>

<script>
   const siteSections = [
    {
        title: 'Things to Do',
        text: 'Browse activities, attractions, shopping places, and popular places across Carlow.',
        link: '/things-to-do/',
        image: '/images/homepage/things-to-do.png'
    },
    {
        title: 'Guides',
        text: 'Read useful, local guides to help plan your visit and discover more of Carlow.',
        link: '/guides/',
        image: '/images/homepage/guides.png'
    },
    {
        title: 'User Reviews',
        text: 'See what visitors think and explore experiences shared by other people.',
        link: '/user-reviews/',
        image: '/images/homepage/user-reviews.png'
    }
   ];
</script>

<!-- Page Container -->
<div class="home-container">
    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>Carlow</h1>
            <p class="hero-text">
                Discover activities, local guides, and visitor reviews to help you plan your trip around Carlow.
            </p>
            <a class="hero-button" href="#explore">Start Exploring</a>
        </div>
    </section>

    <!-- Explore Section -->
    <section class="explore-section" id="explore">
        <h2>Explore the Website</h2>

        <div class="section-grid">
            {#each siteSections as item}
                <div class="section-card">
                    <img src={item.image} alt={item.title} class="section-image" />
                    <h3>{item.title}</h3>
                    <p>{item.text}</p>
                    <a class="section-button" href={item.link}>Explore</a>
                </div>
            {/each}
        </div>
    </section>
</div>


<style>
    .home-container {
        display: flex;
        flex-direction: column;
        gap: var(--space-xl);
    }

    /* Hero Section */
    .hero {
        text-align: center;
        padding: var(--space-xl) var(--space-md);
        border-radius: var(--radius-md);
        background-image: url('/images/backgrounds/carlow-hero.png');
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
        background-blend-mode: overlay;
        background-color: rgba(255, 255, 255, 0.75);
    }

    .hero-content {
        max-width: 800px;
        margin: 0 auto;
    }

    .hero h1 {
        font-size: var(--font-xxl);
        margin-bottom: var(--space-sm);
    }

    .hero-text {
        font-size: var(--font-lg);
        margin-bottom: var(--space-md);
    }

    .hero-button {
        display: inline-block;
        background-color: var(--color-primary);
        color: var(--text-contrast);
        padding: var(--space-sm) var(--space-lg);
        border-radius: var(--radius-sm);
        font-weight: 600;
    }

    .hero-button:hover,
    .hero-button:focus {
        background-color: var(--color-secondary);
    }

    /* Explore Section */
    .explore-section {
        padding: 0 var(--space-md);
        text-align: center;
    }

    .explore-section h2 {
        margin-bottom:  var(--space-lg);
    }

    .section-grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: var(--space-lg);
    }

    .section-image {
        width: 100%;
        height: 220px;
        object-fit: cover;
        border-radius: var(--radius-sm);
        margin-bottom: var(--space-sm);
    }

    .section-card p {
        margin-bottom: var(--space-md);
    }

    .section-button {
        display: inline-block;
        background-color: var(--color-primary);
        color: var(--text-contrast);
        padding: var(--space-sm) var(--space-md);
        border-radius: var(--radius-sm);
        font-weight: 600;
    }

    .section-button:hover,
    .section-button:focus {
        background-color: var(--color-secondary);
    }
    
    @media (max-width: 1024px) {
        .section-grid {
            grid-template-columns: 1fr;
        }

        .section-image {
            height: 200px;
        }
    }
</style>
