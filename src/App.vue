<script setup>
</script>

<template>
  <div class="app">
    <header class="navbar">
      <div class="logo">ReCircle</div>

      <nav>
        <a href="#home">Home</a>
        <a href="#recycling">Recycling Finder</a>
        <a href="#events">Community Events</a>
        <a href="#involved">Get Involved</a>
      </nav>
    </header>

    <main>
      <section id="home" class="hero">
        <div class="hero-content">
          <h1>Give Resources a Second Life</h1>

          <p>
            ReCircle helps communities reduce waste, recycle correctly,
            reuse useful items and participate in local environmental activities.
          </p>

          <a href="#recycling" class="primary-button">
            Find Recycling Options
          </a>
        </div>
      </section>

      <section class="features">
        <h2>Explore ReCircle</h2>

        <div class="feature-grid">
          <div class="feature-card">
            <h3>Recycling Finder</h3>
            <p>
              Find information about how common household items can be recycled.
            </p>
          </div>

          <div class="feature-card">
            <h3>Community Events</h3>
            <p>
              Discover local recycling, clean-up and sustainability events.
            </p>
          </div>

          <div class="feature-card">
            <h3>Get Involved</h3>
            <p>
              Join community activities and contribute to a more sustainable future.
            </p>
          </div>
        </div>
      </section>
    </main>

    <footer>
      <p>© 2026 ReCircle. Supporting a circular community.</p>
    </footer>
  </div>
</template>

<style scoped>
* {
  box-sizing: border-box;
}

.app {
  min-height: 100vh;
  font-family: Arial, Helvetica, sans-serif;
  color: #213547;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 8%;
  background-color: white;
  border-bottom: 1px solid #e5e5e5;
}

.logo {
  font-size: 28px;
  font-weight: bold;
  color: #2e7d32;
}

nav {
  display: flex;
  gap: 24px;
}

nav a {
  text-decoration: none;
  color: #333;
  font-weight: 500;
}

nav a:hover {
  color: #2e7d32;
}

.hero {
  min-height: 520px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 60px 20px;
  background-color: #eef7ee;
}

.hero-content {
  max-width: 760px;
}

.hero h1 {
  font-size: 52px;
  margin-bottom: 20px;
}

.hero p {
  font-size: 20px;
  line-height: 1.6;
  margin-bottom: 30px;
}

.primary-button {
  display: inline-block;
  padding: 14px 24px;
  background-color: #2e7d32;
  color: white;
  text-decoration: none;
  border-radius: 8px;
}

.features {
  padding: 70px 8%;
  text-align: center;
}

.features h2 {
  font-size: 36px;
  margin-bottom: 40px;
}

.feature-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}

.feature-card {
  padding: 30px;
  border: 1px solid #dddddd;
  border-radius: 12px;
  background-color: white;
}

.feature-card h3 {
  color: #2e7d32;
  margin-bottom: 15px;
}

footer {
  text-align: center;
  padding: 25px;
  background-color: #1f2933;
  color: white;
}

@media (max-width: 768px) {
  .navbar {
    flex-direction: column;
    gap: 15px;
  }

  nav {
    flex-direction: column;
    text-align: center;
    gap: 10px;
  }

  .hero h1 {
    font-size: 36px;
  }

  .hero p {
    font-size: 17px;
  }

  .feature-grid {
    grid-template-columns: 1fr;
  }
}
</style>