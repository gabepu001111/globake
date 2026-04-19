<script setup>
import image1 from '../assets/images/image1.jpeg'
import image2 from '../assets/images/image2.jpeg'
import image3 from '../assets/images/image3.jpeg'
import image4 from '../assets/images/image4.jpeg'
import image5 from '../assets/images/image5.jpeg'
import image6 from '../assets/images/image6.jpeg'
import image7 from '../assets/images/image7.jpeg'
import image8 from '../assets/images/image8.jpeg'
import logo from '../assets/images/globakeLogo.jpeg'

const images = [image1, image2, image3, image4, image5, image6, image7, image8]
</script>

<template>
  <div class="app">
    <!-- NAVBAR -->
    <nav class="navbar">
      <div class="nav-left"></div>
      <div class="logo nav-center">
        <img :src="logo" alt="Globake Logo" />
      </div>
      <div class="nav-right">
        <div class="nav-links">
          <router-link to="/menu">Menu</router-link>
          <a href="#">About</a>
          <a href="#">Contact</a>
        </div>
      </div>
    </nav>

    <!-- HERO -->
    <section class="hero">
      <h1>A Global Tasting Experience</h1>
      <p>Made with love in NYC.</p>
      <router-link to="/menu" class="cta">
      <button class="cta">Explore Menu</button>
      </router-link>
    </section>

    <!-- GALLERY -->
    <section class="gallery-section">
      <div class="gallery">
        <div
          v-for="(img, index) in images"
          :key="index"
          class="gallery-item"
        >
          <img :src="img" />
        </div>
      </div>
    </section>

    <!-- FOOTER -->
    <footer class="footer">
      <p>© 2026 Globake</p>
    </footer>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&display=swap');

.app {
  background: #0f2f23;
  color: #f5f1e8;
  min-height: 100vh;
  font-family: 'Inter', sans-serif;
  display: flex;
  flex-direction: column;
}

/* NAVBAR */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 60px;
  position: sticky;
  top: 0;
  backdrop-filter: blur(10px);
  background: rgba(15, 47, 35, 0.7);
}

.nav-center {
  flex: 1;
  display: flex;
  justify-content: center;
  transform: translateX(80px);
}

.nav-left, .nav-right {
  flex: 0;
}

.nav-links {
  display: flex;
  gap: 30px;
}

.nav-links a {
  text-decoration: none;
  color: #f5f1e8;
  font-weight: 400;
  font-size: 0.95rem;
  opacity: 0.8;
  transition: all 0.2s ease;
}

.nav-links a:hover {
  opacity: 1;
}

/* HERO */
.hero {
  text-align: center;
  padding: 120px 20px 80px;
}

.hero h1 {
  font-size: 3.5rem;
  font-weight: 600;
  letter-spacing: -1px;
}

.hero p {
  margin-top: 15px;
  font-size: 1.1rem;
  opacity: 0.85;
}

.cta {
  margin-top: 30px;
  padding: 12px 26px;
  border-radius: 999px;
  border: none;
  background: #f5f1e8;
  color: #0f2f23;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.2s ease;
}

.cta:hover {
  transform: translateY(-2px);
}

/* GALLERY */
.gallery-section {
  display: flex;
  justify-content: center;
  padding-bottom: 80px;
}

.gallery {
  width: 100%;
  max-width: 1100px;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 20px;
  padding: 0 20px;
}

.gallery-item {
  overflow: hidden;
  border-radius: 18px;
  background: rgba(255, 255, 255, 0.03);
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}

.gallery-item img {
  width: 100%;
  height: 300px;
  object-fit: cover;
  display: block;
  transition: transform 0.3s ease;
}

.gallery-item:hover {
  transform: translateY(-6px);
  box-shadow: 0 15px 40px rgba(0,0,0,0.3);
}

.gallery-item:hover img {
  transform: scale(1.05);
}

/* FOOTER */
.footer {
  text-align: center;
  padding: 30px;
  opacity: 0.6;
  font-size: 0.9rem;
}

/* Logo */
.nav-center img {
  height: 110px;
  width: auto;
  object-fit: contain;
}


</style>
