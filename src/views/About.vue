<script setup>
const person = {
  name: "Nitya Nagarajan",
  title: "Investment Associate",
  location: "New York, New York 🇺🇸",
  email: "nitya.nagarajann@gmail.com",
  education: "The University of Texas at Dallas",
  company: "Assurant",
  description:
    "Hi, my name is Nitya — I have been baking since I was a kid, turning kitchens into little worlds of warmth, sugar, and imagination. What started as mixing flour just for fun has grown into a deep passion for creating cookies that tell stories, bring comfort, and travel across cultures in every bite.",
}

const highlights = [
  {
    title: "Charles Schwab Internship",
    description:
      "Selected as Investment Analyst Intern, focused on investment research and wealth management strategies.",
    color: "#b8d8ff"
  },
  {
    title: "Koch Industries Internship",
    description:
      "Worked in a high-paced environment supporting analytical and financial decision-making processes.",
    color: "#ffd6a5"
  },
  {
    title: "UT Dallas Graduate",
    description:
      "Studied finance-related disciplines with strong exposure to investment theory and applied analytics.",
    color: "#cdb4db"
  }
]
</script>

<template>
  <div class="about-page">
    <!-- HERO -->
    <div class="hero">
      <h1>{{ person.name }}</h1>
      <p class="role">{{ person.title }}</p>
      <p class="location">{{ person.location }}</p>
    </div>

    <!-- ABOUT CARD -->
    <div class="about-card">
      <h2>About</h2>
      <p>{{ person.description }}</p>

      <div class="meta">
        <p><strong>Company:</strong> {{ person.company }}</p>
        <p><strong>Education:</strong> {{ person.education }}</p>
        <p><strong>Contact:</strong> {{ person.email }}</p>
      </div>
    </div>

    <!-- HIGHLIGHTS -->
    <h2 class="section-title">Highlights</h2>

    <div class="grid">
      <div
        v-for="item in highlights"
        :key="item.title"
        class="card"
      >
        <div class="accent" :style="{ background: item.color }"></div>
        <h3>{{ item.title }}</h3>
        <p>{{ item.description }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.about-page {
  min-height: 100vh;
  background: #0f2f23;
  color: #f5f1e8;
  padding: 80px 20px;
  font-family: 'Inter', sans-serif;
}

/* HERO */
.hero {
  text-align: center;
  margin-bottom: 50px;
}

.hero h1 {
  font-size: 3rem;
  font-weight: 600;
}

.role {
  font-size: 1.2rem;
  opacity: 0.85;
  margin-top: 10px;
}

.location {
  font-size: 0.95rem;
  opacity: 0.6;
  margin-top: 5px;
}

/* ABOUT CARD */
.about-card {
  max-width: 800px;
  margin: 0 auto;
  background: rgba(255, 255, 255, 0.03);
  padding: 25px;
  border-radius: 20px;
  backdrop-filter: blur(10px);
  transition: transform 0.25s ease;
}

.about-card:hover {
  transform: translateY(-4px);
}

.about-card h2 {
  margin-bottom: 10px;
}

.about-card p {
  opacity: 0.85;
  line-height: 1.6;
}

.meta {
  margin-top: 20px;
  font-size: 0.9rem;
  opacity: 0.75;
}

/* SECTION TITLE */
.section-title {
  text-align: center;
  margin-top: 60px;
  font-size: 2rem;
}

/* GRID */
.grid {
  margin-top: 30px;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 25px;
  max-width: 1000px;
  margin-left: auto;
  margin-right: auto;
}

/* CARD */
.card {
  background: rgba(255, 255, 255, 0.03);
  border-radius: 20px;
  padding: 20px;
  backdrop-filter: blur(10px);
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}

.card:hover {
  transform: translateY(-6px);
  box-shadow: 0 15px 40px rgba(0,0,0,0.3);
}

.accent {
  height: 6px;
  width: 60px;
  border-radius: 10px;
  margin-bottom: 12px;
}

.card h3 {
  margin: 0;
  font-size: 1.1rem;
}

.card p {
  margin-top: 10px;
  font-size: 0.9rem;
  opacity: 0.8;
  line-height: 1.5;
}
</style>