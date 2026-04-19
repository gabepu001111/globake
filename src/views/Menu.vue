<script setup>
const cookies = [
  {
    name: "Cinnamon Cookie Dough",
    country: "USA 🇺🇸",
    description:
      "A warm, nostalgic blend of classic cookie dough with a cinnamon twist—soft, gooey, and dangerously addictive.",
    color: "#d6a77a"
  },
  {
    name: "Sakura Matcha",
    country: "Japan 🇯🇵",
    description:
      "Earthy matcha meets delicate sakura sweetness. Light, floral, and beautifully balanced.",
    color: "#e8b4c8"
  },
  {
    name: "Dubai Chocolate Chip",
    country: "Dubai 🇦🇪",
    description:
      "Rich chocolate chips infused with a luxurious Middle Eastern touch—deep, bold, and indulgent.",
    color: "#c69c6d"
  },
  {
    name: "Gulab Jamun",
    country: "India 🇮🇳",
    description:
      "A fusion of syrupy gulab jamun that is aromatic and unforgettable.",
    color: "#f0c27b"
  }
]
</script>

<template>
  <div class="menu-page">
    <h1>Our Menu</h1>
    <p class="subtitle">Flavors from around the world</p>

    <div class="grid">
      <div
        v-for="cookie in cookies"
        :key="cookie.name"
        class="card"
      >
        <div class="accent" :style="{ background: cookie.color }"></div>

        <h2>{{ cookie.name }}</h2>
        <span class="country">{{ cookie.country }}</span>
        <p>{{ cookie.description }}</p>

        <button>Order Soon</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.menu-page {
  min-height: 100vh;
  background: #0f2f23;
  color: #f5f1e8;
  padding: 80px 20px;
  text-align: center;
  font-family: 'Inter', sans-serif;
}

h1 {
  font-size: 3rem;
  font-weight: 600;
}

.subtitle {
  margin-top: 10px;
  opacity: 0.8;
}

/* GRID */
.grid {
  margin-top: 50px;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 30px;
  max-width: 1000px;
  margin-left: auto;
  margin-right: auto;
}

/* CARD */
.card {
  background: rgba(255, 255, 255, 0.03);
  border-radius: 20px;
  padding: 25px;
  text-align: left;
  backdrop-filter: blur(10px);
  position: relative;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}

.card:hover {
  transform: translateY(-6px);
  box-shadow: 0 15px 40px rgba(0,0,0,0.3);
}

/* accent bar */
.accent {
  height: 6px;
  width: 60px;
  border-radius: 10px;
  margin-bottom: 15px;
}

.card h2 {
  margin: 0;
  font-size: 1.3rem;
}

.country {
  font-size: 0.9rem;
  opacity: 0.7;
}

.card p {
  margin-top: 10px;
  font-size: 0.95rem;
  line-height: 1.5;
  opacity: 0.85;
}

button {
  margin-top: 15px;
  padding: 8px 16px;
  border-radius: 999px;
  border: none;
  background: #f5f1e8;
  color: #0f2f23;
  cursor: pointer;
  font-size: 0.9rem;
}

button:hover {
  opacity: 0.8;
}
</style>