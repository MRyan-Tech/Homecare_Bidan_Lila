<template>
  <div class="main-container">
    <!-- Hero Section -->
    <div class="hero_area">
      <!-- Background -->
      <div class="bg-box">
        <img src="/images/Bg-Homecare.jpg" alt="Background" class="bg-image" />
      </div>

      <!-- Hero Content -->
      <div class="hero-content container" style="">
        <!-- Kiri: Gambar Brosur -->
        <div class="left-box animate-zoom-in">
          <img
            src="/images/image1.jpg"
            alt="Mom Baby Spa Info"
            class="spa-info-img "style="transform: scale(1.05); transition: all 0.3s ease;"
          />
        </div>

        <!-- Kanan: Sambutan -->
        <div class="right-box animate-zoom-in">
          <h1>Selamat datang di <br /><strong>Homecare Bidan Lila</strong></h1>
          <p>
            Tim bidan berpengalaman siap mendukung Anda dengan layanan yang ramah dan penuh kasih se-Jabodetabek.
          </p>
          <a href="https://wa.me/6281365417753" target="_blank" class="btn-consult">
            💬 Konsultasi Online Gratis
          </a>
        </div>
      </div>
    </div>

    <!-- Komponen Lain -->
    <div class="content-sections">
      <!-- <offer /> -->
      <!-- <food /> -->
      <about />
      <client />
    </div>
  </div>
</template>


<script>
import Offer from "../components/offer.vue";
import food from "../components/food.vue";
import about from "../components/about.vue";
import client from "../components/client.vue";

export default {
  components: {
    Offer,
    food,
    about,
    client,
  },
};
</script>

<style scoped>
.main-container {
  position: relative;
  width: 100%;
  overflow-x: hidden;
}

.bg-box {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
}

.bg-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: blur(4px);
}

.bg-box::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.4);
}

/* Hero Content */
.hero-content {
  position: relative;
  z-index: 2;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  padding: 130px 20px 80px;
  gap: 40px;
  color: white;
  text-align: center;
}

.left-box,
.right-box {
  flex: 1 1 320px;
  max-width: 500px;
}

.spa-info-img {
  width: 100%;
  max-height: 360px;

    border-radius: 30px;
    border: 5px solid white;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    transition: transform 0.3s ease-in-out;
}

.right-box h1 {
  font-size: 2.2rem;
  margin-bottom: 1rem;
  line-height: 1.3;
}

.right-box p {
  font-size: 1.1rem;
  margin-bottom: 1.5rem;
}

.btn-consult {
  display: inline-block;
  background-color: #00c853;
  color: white;
  font-weight: 600;
  padding: 14px 26px;
  border-radius: 10px;
  text-decoration: none;
  box-shadow: 0 4px 12px rgba(0, 200, 83, 0.4);
  transition: all 0.3s ease;
}

.btn-consult:hover {
  background-color: #00b34a;
  transform: scale(1.05);
  box-shadow: 0 6px 16px rgba(0, 179, 74, 0.5);
}

/* Animations */
@keyframes fade-in {
  0% { opacity: 0; transform: translateY(20px); }
  100% { opacity: 1; transform: translateY(0); }
}
@keyframes zoom-in {
  0% { transform: scale(0.9); opacity: 0; }
  100% { transform: scale(1); opacity: 1; }
}

.animate-fade-in {
  animation: fade-in 0.8s ease forwards;
}

.animate-zoom-in {
  animation: zoom-in 0.8s ease forwards;
}

/* Responsive typography */
@media (max-width: 768px) {
  .right-box h1 {
    font-size: 1.8rem;
  }

  .right-box p {
    font-size: 1rem;
  }

  .btn-consult {
    padding: 12px 20px;
    font-size: 0.95rem;
  }

  .spa-info-img {
    max-height: 280px;
  }
}

/* Section bawah */
.content-sections {
  position: relative;
  z-index: 2;
  padding: 40px 20px 60px;
}
</style>
