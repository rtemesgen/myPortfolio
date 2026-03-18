<template>
  <header class="site-header panel panel-strong">
    <div class="brand">
      <p class="eyebrow">Developer Portfolio</p>
      <router-link to="/" class="brand-name">{{ contact.name }}</router-link>
    </div>

    <nav class="nav-links">
      <router-link to="/">Overview</router-link>
      <router-link to="/projects">Projects</router-link>
      <router-link to="/experience">Experience</router-link>
    </nav>

    <div class="header-actions">
      <a :href="contact.cvFile" download class="button-pill">
        Download CV
      </a>
      <a
        :href="contact.whatsappLink"
        target="_blank"
        rel="noopener noreferrer"
        class="button-pill button-whatsapp"
      >
        WhatsApp
      </a>
      <a :href="`mailto:${contact.email}`" class="button-pill button-primary">Contact</a>
    </div>
  </header>
</template>

<script setup>
import { contact } from '../data/portfolio'
</script>

<style scoped>
.site-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
  padding: 10px 14px;
  margin-bottom: 10px;
}

.brand-name {
  font-family: Georgia, 'Times New Roman', serif;
  font-size: 0.98rem;
  color: #10233f;
}

.nav-links {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

.nav-links a {
  padding: 7px 11px;
  border-radius: 999px;
  color: #4e6380;
  font-size: 0.86rem;
}

.nav-links a.router-link-active {
  background: rgba(31, 79, 145, 0.1);
  color: #163c6c;
  font-weight: 600;
}

.header-actions {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

@media (max-width: 760px) {
  .site-header {
    display: grid;
  }

  .nav-links {
    order: 3;
  }
}
</style>
