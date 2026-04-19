<script>
    import { asset } from '$app/paths';
    import Navigation from './Navigation.svelte';
</script>


<header class="header">
    <a href="/" class="logo-area">
        <img src={asset("/logo.png")} alt="Site Logo" />
    </a>
    <Navigation />
</header>


<style>
    .header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0 var(--space-lg);
        background-color: var(--color-secondary);
        box-shadow: var(--shadow-md);
        border-bottom: var(--border-default);
        position: relative;
        z-index: 100;
    }

    .logo-area {
        display: flex;
        align-items: center;
        gap: var(--space-sm);
        font-family: var(--font-heading);
    }

    .logo-area img {
        width: 96px;
        height: auto;
        border-radius: 0;
        box-shadow: none;
    }

    @keyframes fadeInTitle {
        from {
            opacity: 0;
            transform: translateY(10px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    @media (max-width: 768px) {
        .header {
            flex-direction: column;
            align-items: flex-start;
            padding: var(--space-sm);
        }

        .logo-area {
            justify-content: center;
            width: 100%;
        }

    }
</style>
