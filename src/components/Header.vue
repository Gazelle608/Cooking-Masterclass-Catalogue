<template>
    <header class="header">
        <div class="container">
            <div class="logo">
                <h1>🍳 Cooking Masterclass</h1>
            </div>
            <div class="whishlist-counter">
                <span class="heart">❤️</span>
                <span class="count">{{ wishlistCount }}</span>
                <span class="label">Saved Classes</span>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: 'AppHeader',
    props: {
        wishlistCount: {
            type: Number,
            required: true,
            default: 0
        }
    }
}
</script>

<style scoped>
.header {
    background: linear-gradient(135deg, #ff6b6b, #ee5a24);
    color: white;
    padding: 1rem 0;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo h1 {
    margin: 0;
    font-size: 1.8rem;
    font-weight: 700;
}

.wishlist-counter {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    background: rgba(255,255,255,0.2);
    padding: 0.5rem 1rem;
    border-radius: 25px;
    backdrop-filter: blur(10px);
}

.heart {
    font-size: 1.2rem;
}

.count {
    font-weight: bold;
    font-size: 1.1rem;
}

.label {
    font-size: 0.9rem;
    opacity: 0.9;
}

@media (max-width: 768px) {
    .logo h1 {
        font-size: 1.4rem;
    }

    .wishlist-counter {
        padding: 04rem 0.8rem;
    }
}
</style>