<template>
  <div class="page-stack">
    <InfoPanel eyebrow="Projects" title="Software work">
      <p class="muted intro">
        These projects highlight my growth as a full-stack developer, from practical business
        systems to focused frontend learning and assessment work.
      </p>
    </InfoPanel>

    <section class="project-grid">
      <ProjectCard v-for="project in projects" :key="project.name" :project="project" />
    </section>

    <section class="grid-two">
      <InfoPanel eyebrow="Stack" title="Tools I use">
        <div class="chip-row">
          <span v-for="skill in skills" :key="skill" class="chip">{{ skill }}</span>
        </div>
      </InfoPanel>

      <InfoPanel eyebrow="Contact" title="Let&apos;s build">
        <p class="muted intro">
          I&apos;m open to junior developer opportunities and hands-on technical work where I can
          contribute, learn fast, and keep building useful systems.
        </p>
        <div class="button-row">
          <a :href="`mailto:${contact.email}`" class="button-pill button-primary">Email Me</a>
          <a :href="contact.github" target="_blank" rel="noopener noreferrer" class="button-pill">
            GitHub
          </a>
        </div>
      </InfoPanel>
    </section>
  </div>
</template>

<script setup>
import InfoPanel from '../components/InfoPanel.vue'
import ProjectCard from '../components/ProjectCard.vue'
import { contact, projects, skills } from '../data/portfolio'
</script>

<style scoped>
.intro {
  font-size: 0.84rem;
  line-height: 1.4;
}

.project-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 10px;
  align-items: stretch;
}

@media (max-width: 720px) {
  .project-grid {
    grid-template-columns: 1fr;
  }
}
</style>
