<script setup>
// Component name is automatically inferred from the filename
</script>

<template>
    <nav class="navbar">
        <div class="nav-brand">URL Shortener</div>
        <div class="nav-links">
            <router-link to="/">Home</router-link>
            <router-link to="/my-urls">My URLs</router-link>
            <router-link to="/profile">Profile</router-link>
        </div>
    </nav>
</template>

<style scoped>
.navbar {
    background-color: #2c3e50;
    padding: 1rem 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: sticky;
    top: 0;
    z-index: 1000;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    width: 100%;
}

.nav-brand {
    color: white;
    font-size: 1.5rem;
    font-weight: bold;
}

.nav-links {
    display: flex;
    gap: 1.5rem;
}

.nav-links a {
    color: white;
    text-decoration: none;
    padding: 0.5rem 1rem;
    border-radius: 4px;
    transition: all 0.3s ease;
}

.nav-links a:hover {
    background-color: #34495e;
}

.nav-links a.router-link-active {
    background-color: #34495e;
} 

@media (max-width: 768px) {
  .navbar {
    padding: 1rem;
    flex-direction: column;
    gap: 1rem;
  }

  .nav-links {
    width: 100%;
    justify-content: center;
  }
}
</style> 