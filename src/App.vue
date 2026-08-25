<script setup>
import { ref, computed } from 'vue'

const searchTerm = ref('')

const recyclingItems = ref([
  {
    name: 'Plastic Bottle',
    category: 'Plastic',
    instruction: 'Rinse the bottle and place it in the recycling bin.',
  },
  {
    name: 'Glass Jar',
    category: 'Glass',
    instruction: 'Remove the lid and place the clean jar in the recycling bin.',
  },
  {
    name: 'Cardboard Box',
    category: 'Paper',
    instruction: 'Flatten the box before placing it in the recycling bin.',
  },
  {
    name: 'Aluminium Can',
    category: 'Metal',
    instruction: 'Rinse the can and place it in the recycling bin.',
  },
  {
    name: 'Newspaper',
    category: 'Paper',
    instruction: 'Keep it dry and place it in the paper recycling bin.',
  },
])

const filteredItems = computed(() => {
  return recyclingItems.value.filter((item) =>
    item.name.toLowerCase().includes(searchTerm.value.toLowerCase()),
  )
})

const events = ref([
  {
    id: 1,
    title: 'Community Clean-Up Day',
    date: '5 September 2026',
    location: 'Carlton Gardens',
    description:
      'Join local volunteers to collect litter and help keep our community clean.',
  },
  {
    id: 2,
    title: 'Recycling Workshop',
    date: '12 September 2026',
    location: 'Community Centre',
    description:
      'Learn how to correctly sort household waste and reduce recycling contamination.',
  },
  {
    id: 3,
    title: 'Clothing Swap Event',
    date: '20 September 2026',
    location: 'ReCircle Community Hub',
    description:
      'Bring unwanted clothes and exchange them for useful pre-loved items.',
  },
])
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
      <section id="recycling" class="recycling-section">
        <div class="section-container">
          <h2>Recycling Finder</h2>

          <p class="section-description">
            Search for an item to learn how it can be recycled correctly.
          </p>

          <input
            v-model="searchTerm"
            type="text"
            class="search-input"
            placeholder="Search for an item..."
          />

          <div class="recycling-grid">
            <div
              v-for="item in filteredItems"
              :key="item.name"
              class="recycling-card"
            >
              <h3>{{ item.name }}</h3>

              <p>
                <strong>Category:</strong>
                {{ item.category }}
              </p>

              <p>
                {{ item.instruction }}
              </p>
            </div>
          </div>

          <p v-if="filteredItems.length === 0" class="no-results">
            No recycling information found.
          </p>
        </div>
      </section>
      <section id="events" class="events-section">
        <div class="section-container">
          <h2>Community Events</h2>

          <p class="section-description">
            Discover upcoming activities and connect with your local community.
          </p>

          <div class="events-grid">
            <article
              v-for="event in events"
              :key="event.id"
              class="event-card"
            >
              <h3>{{ event.title }}</h3>

              <p>
                <strong>Date:</strong>
                {{ event.date }}
              </p>

              <p>
                <strong>Location:</strong>
                {{ event.location }}
              </p>

              <p>{{ event.description }}</p>

              <a href="#involved" class="event-button">
                Join Event
              </a>
            </article>
          </div>
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

.events-section {
  padding: 70px 8%;
  background-color: white;
}

.events-section h2 {
  text-align: center;
  font-size: 36px;
  margin-bottom: 10px;
}

.events-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  margin-top: 35px;
}

.event-card {
  padding: 28px;
  border: 1px solid #dddddd;
  border-radius: 12px;
  background-color: #ffffff;
}

.event-card h3 {
  color: #2e7d32;
  margin-bottom: 18px;
}

.event-card p {
  line-height: 1.6;
}

.event-button {
  display: inline-block;
  margin-top: 12px;
  padding: 10px 18px;
  background-color: #2e7d32;
  color: white;
  text-decoration: none;
  border-radius: 7px;
}

.event-button:hover {
  background-color: #256629;
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

  .recycling-grid {
  grid-template-columns: 1fr;
  }

  .events-grid {
  grid-template-columns: 1fr;
  }
}
.recycling-section {
  padding: 70px 8%;
  background-color: #f7faf7;
}

.section-container {
  max-width: 1100px;
  margin: 0 auto;
}

.recycling-section h2 {
  text-align: center;
  font-size: 36px;
  margin-bottom: 10px;
}

.section-description {
  text-align: center;
  margin-bottom: 30px;
  font-size: 18px;
}

.search-input {
  display: block;
  width: 100%;
  max-width: 600px;
  margin: 0 auto 35px;
  padding: 14px 16px;
  border: 1px solid #cccccc;
  border-radius: 8px;
  font-size: 16px;
}

.search-input:focus {
  outline: 2px solid #2e7d32;
  border-color: #2e7d32;
}

.recycling-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}

.recycling-card {
  background-color: white;
  padding: 25px;
  border: 1px solid #dddddd;
  border-radius: 12px;
}

.recycling-card h3 {
  color: #2e7d32;
  margin-bottom: 15px;
}

.no-results {
  text-align: center;
  margin-top: 25px;
  font-weight: bold;
}
</style>