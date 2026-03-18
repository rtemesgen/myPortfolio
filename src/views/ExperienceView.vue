<template>
  <div class="page-stack">
    <section class="grid-two">
      <InfoPanel eyebrow="Experience" title="Career journey">
        <p class="muted intro">
          My background combines software development with long-term technical field work,
          operations, repair, networking, and client support.
        </p>
      </InfoPanel>

      <InfoPanel eyebrow="Languages" title="Communication">
        <div class="grid-two language-grid">
          <div v-for="language in languages" :key="language.name" class="language-item">
            <strong>{{ language.name }}</strong>
            <span>{{ language.level }}</span>
          </div>
        </div>
      </InfoPanel>
    </section>

    <section class="experience-grid">
      <ExperienceCard v-for="role in experience" :key="role.title + role.company" :role="role" />
    </section>

    <section class="grid-two">
      <InfoPanel eyebrow="Education" title="Academic background">
        <div class="education-list">
          <div v-for="item in education" :key="item.title" class="education-item">
            <h3>{{ item.title }}</h3>
            <p class="muted">{{ item.school }}</p>
            <span>{{ item.period }}</span>
          </div>
        </div>
      </InfoPanel>

      <InfoPanel eyebrow="Strengths" title="Additional strengths">
        <ul class="list-clean">
          <li v-for="item in strengths" :key="item">{{ item }}</li>
        </ul>
      </InfoPanel>
    </section>
  </div>
</template>

<script setup>
import ExperienceCard from '../components/ExperienceCard.vue'
import InfoPanel from '../components/InfoPanel.vue'
import { education, experience, languages, strengths } from '../data/portfolio'
</script>

<style scoped>
.intro {
  font-size: 0.84rem;
  line-height: 1.4;
}

.experience-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
  gap: 10px;
}

.language-item,
.education-item {
  padding: 10px;
  border: 1px solid var(--line);
  border-radius: 18px;
  background: rgba(31, 79, 145, 0.04);
}

.language-item strong,
.education-item h3 {
  font-size: 0.88rem;
}

.language-item span,
.education-item span {
  display: block;
  margin-top: 6px;
  color: var(--muted);
  font-size: 0.76rem;
}

.education-list {
  display: grid;
  gap: 6px;
}
</style>
