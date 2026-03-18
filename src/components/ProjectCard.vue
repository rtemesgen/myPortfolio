<template>
  <article class="project-card panel">
    <div class="top-row">
      <div>
        <h3>{{ project.name }}</h3>
        <p class="muted">{{ project.summary }}</p>
      </div>
      <span class="type-pill">{{ project.type }}</span>
    </div>

    <div class="chip-row">
      <span v-for="item in project.stack" :key="item" class="chip">{{ item }}</span>
    </div>

    <ul class="list-clean">
      <li v-for="point in project.points" :key="point">{{ point }}</li>
    </ul>

    <div class="button-row links">
      <a
        v-for="link in project.links"
        :key="link.label"
        :href="link.href"
        target="_blank"
        rel="noopener noreferrer"
        class="button-pill"
      >
        {{ link.label }}
      </a>
    </div>
  </article>
</template>

<script setup>
defineProps({
  project: {
    type: Object,
    required: true,
  },
})
</script>

<style scoped>
.project-card {
  padding: 14px;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.top-row {
  display: flex;
  justify-content: space-between;
  gap: 10px;
  align-items: start;
}

.top-row h3 {
  font-size: 0.92rem;
  line-height: 1.2;
}

.top-row p {
  font-size: 0.82rem;
  line-height: 1.4;
}

.type-pill {
  flex-shrink: 0;
  padding: 5px 9px;
  border-radius: 999px;
  background: rgba(217, 151, 47, 0.16);
  color: #895616;
  font-size: 0.64rem;
  font-weight: 700;
}

.links {
  margin-top: 16px;
  margin-top: auto;
  padding-top: 10px;
}

@media (max-width: 720px) {
  .top-row {
    display: grid;
  }
}
</style>
