<template>
  <div class="page-stack">
    <section class="hero-grid">
      <article class="panel section-card hero-main">
        <p class="eyebrow">Overview</p>
        <h1>{{ contact.title }}</h1>
        <p class="hero-name headline-font">{{ contact.name }}</p>
        <p class="hero-copy">
          I build practical web applications with Vue.js, Node.js, Express, and MongoDB,
          while also bringing deep hands-on experience in phone repair, CCTV installation,
          networking, and technical support across Eritrea, South Sudan, and Uganda.
        </p>

        <div class="button-row">
          <a :href="contact.github" target="_blank" rel="noopener noreferrer" class="button-pill button-primary">
            View GitHub
          </a>
          <router-link to="/projects" class="button-pill">See Projects</router-link>
          <router-link to="/experience" class="button-pill">See Experience</router-link>
        </div>
      </article>

      <article class="panel section-card hero-side">
        <p class="eyebrow">Quick Facts</p>
        <div class="fact-list">
          <div>
            <span>Location</span>
            <strong>{{ contact.location }}</strong>
          </div>
          <div>
            <span>Email</span>
            <strong>{{ contact.email }}</strong>
          </div>
          <div>
            <span>Phone</span>
            <strong>{{ contact.phone }}</strong>
          </div>
        </div>
      </article>
    </section>

    <section class="grid-two">
      <InfoPanel eyebrow="Profile" title="Professional summary">
        <p class="muted body-copy">
          Motivated junior full-stack developer with hands-on experience building secure web
          applications, implementing JWT authentication, role-based access control, REST APIs,
          and MongoDB-backed systems. My technical journey also includes field service work in
          networking, CCTV installation, systems maintenance, and mobile device repair.
        </p>
      </InfoPanel>

      <InfoPanel eyebrow="Snapshot" title="Highlights">
        <div class="grid-two stat-grid">
          <div v-for="item in highlights" :key="item.label" class="stat-item">
            <strong>{{ item.value }}</strong>
            <span>{{ item.label }}</span>
          </div>
        </div>
      </InfoPanel>
    </section>

    <section class="grid-two overview-lower">
      <InfoPanel eyebrow="Focus" title="What I do">
        <div class="chip-row">
          <span v-for="item in focusAreas" :key="item" class="chip">{{ item }}</span>
        </div>
      </InfoPanel>

      <InfoPanel eyebrow="Featured" title="Main project">
        <ProjectCard :project="projects[0]" />
      </InfoPanel>
    </section>
  </div>
</template>

<script setup>
import InfoPanel from '../components/InfoPanel.vue'
import ProjectCard from '../components/ProjectCard.vue'
import { contact, focusAreas, highlights, projects } from '../data/portfolio'
</script>

<style scoped>
.hero-grid {
  display: grid;
  grid-template-columns: 1.25fr 0.75fr;
  gap: 20px;
}

.hero-main {
  min-height: 320px;
  background:
    linear-gradient(135deg, rgba(255, 248, 237, 0.98), rgba(238, 251, 246, 0.94));
}

.hero-side {
  background: linear-gradient(180deg, #0e5364, #15738a);
  color: #eff6ff;
}

.hero-side .eyebrow,
.hero-side span {
  color: rgba(239, 246, 255, 0.76);
}

h1 {
  margin-bottom: 6px;
  font-size: clamp(2.3rem, 5vw, 4rem);
  line-height: 1;
}

.hero-name {
  margin-bottom: 16px;
  font-size: 1.3rem;
  color: var(--accent);
}

.hero-copy,
.body-copy {
  line-height: 1.75;
}

.fact-list {
  display: grid;
  gap: 16px;
}

.fact-list div {
  padding: 16px;
  border-radius: 18px;
  background: rgba(255, 255, 255, 0.08);
  transition: transform 160ms ease, background-color 160ms ease;
}

.fact-list div:hover {
  transform: translateY(-2px);
  background: rgba(255, 255, 255, 0.14);
}

.fact-list span {
  display: block;
  margin-bottom: 8px;
  font-size: 0.75rem;
  letter-spacing: 0.14em;
  text-transform: uppercase;
}

.fact-list strong {
  font-size: 1rem;
  line-height: 1.5;
}

.stat-grid {
  gap: 12px;
}

.stat-item {
  padding: 16px;
  border: 1px solid var(--line);
  border-radius: 18px;
  background: linear-gradient(135deg, rgba(255, 245, 226, 0.86), rgba(237, 251, 247, 0.86));
  transition:
    transform 160ms ease,
    box-shadow 160ms ease,
    border-color 160ms ease;
}

.stat-item:hover {
  transform: translateY(-3px);
  border-color: rgba(15, 95, 115, 0.18);
  box-shadow: 0 14px 28px rgba(28, 66, 78, 0.12);
}

.stat-item strong {
  display: block;
  font-size: 1.15rem;
  color: var(--brand-strong);
}

.stat-item span {
  display: block;
  margin-top: 6px;
  color: var(--muted);
  line-height: 1.45;
}

.overview-lower {
  align-items: start;
}

@media (max-width: 900px) {
  .hero-grid {
    grid-template-columns: 1fr;
  }
}
</style>
