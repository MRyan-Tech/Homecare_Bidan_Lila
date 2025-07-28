<template>
  <nav class="navbar navbar-expand-lg navbar-dark px-3 py-3 shadow-sm">
    <div class="container-fluid">
      <!-- Logo & Brand -->
      <router-link to="/" class="navbar-brand d-flex align-items-center">
        <img src="/images/Logo.png" alt="Logo" style="width: 60px;" class="me-2" />
        <span class="fs-3 fw-semibold text-white">Homecare Bidan Lila</span>
      </router-link>

      <!-- Toggle Button -->
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNavDropdown"
        aria-controls="navbarNavDropdown"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <!-- Nav Items -->
      <div class="collapse navbar-collapse mt-2 mt-lg-0" id="navbarNavDropdown">
        <ul class="navbar-nav ms-auto mb-2 mb-lg-0 align-items-lg-center">
          <li class="nav-item" :class="{ active: route.path === '/' }">
            <router-link class="nav-link" to="/">Home</router-link>
          </li>
          <li class="nav-item" :class="{ active: route.path === '/about' }">
            <router-link class="nav-link" to="/about">About Me</router-link>
          </li>

          <!-- List Treatment Dropdown -->
          <li class="nav-item dropdown">
            <a
              class="nav-link dropdown-toggle"
              href="#"
              id="treatmentDropdown"
              role="button"
              data-bs-toggle="dropdown"
              aria-expanded="false"
            >
              List Treatment
            </a>
            <ul class="dropdown-menu dropdown-menu-end shadow" aria-labelledby="treatmentDropdown">
              <li><router-link class="dropdown-item" to="/treatment/mom">Mom Treatment</router-link></li>
              <li><router-link class="dropdown-item" to="/treatment/baby">Baby Treatment</router-link></li>
              <li><router-link class="dropdown-item" to="/treatment/kids">Kids Treatment</router-link></li>
              <li><router-link class="dropdown-item" to="/treatment/mom-baby">Mom & Baby Treatment</router-link></li>
            </ul>
          </li>

          <!-- Mini Shop Dropdown -->
          <li class="nav-item dropdown">
            <a
              class="nav-link dropdown-toggle"
              href="#"
              id="shopDropdown"
              role="button"
              data-bs-toggle="dropdown"
              aria-expanded="false"
            >
              Mini Shop
            </a>
            <ul class="dropdown-menu dropdown-menu-end shadow" aria-labelledby="shopDropdown">
              <li><router-link class="dropdown-item" to="/shop/baby">Product Baby</router-link></li>
              <li><router-link class="dropdown-item" to="/shop/mom">Product Mom</router-link></li>
              <li><router-link class="dropdown-item" to="/shop/kids">Product Kids</router-link></li>
            </ul>
          </li>
          <li class="nav-item" :class="{ active: route.path === '/about' }">
            <router-link class="nav-link" to="/about">Artikel</router-link>
          </li>
          <!-- Cart Icon -->
          <li class="nav-item mx-2">
            <router-link class="nav-link position-relative" to="/cart">
              <i class="fas fa-shopping-cart fs-5"></i>
              <span class="visually-hidden">Cart</span>
            </router-link>
          </li>
        </ul>

        <!-- Search Form -->
        <form class="d-flex ms-lg-3 mt-3 mt-lg-0" role="search">
          <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search" />
          <button class="btn btn-light" type="submit">Search</button>
        </form>
      </div>
    </div>
  </nav>
</template>

<script>
import { useRoute } from "vue-router";

export default {
  setup() {
    const route = useRoute();
    return { route };
  }
};
</script>

<style scoped>
.navbar {
  background-color: #02345f;
}
.navbar-nav .nav-link {
  color: #ffffff !important;
  font-weight: 500;
  transition: color 0.3s ease;
}

.navbar-nav .nav-link:hover {
  color: #ffc107 !important;
}

.navbar-nav .nav-item.active .nav-link {
  color: #ffc107 !important;
  font-weight: 600;
  position: relative;
}

.navbar-nav .nav-item.active .nav-link::after {
  content: "";
  display: block;
  height: 2px;
  background-color: #ffc107;
  margin-top: 4px;
  transition: width 0.3s ease;
}

.dropdown-menu .dropdown-item:hover {
  background-color: #f8f9fa;
  color: #044680;
}

@media (max-width: 991px) {
  .navbar-nav {
    background-color: #02345f;
    border-radius: 8px;
    padding: 1rem;
    margin-top: 1rem;
  }
}
</style>
