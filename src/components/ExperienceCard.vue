<template>
  <article class="experience-card panel">
    <div class="top-row">
      <div>
        <h3>{{ role.title }}</h3>
        <p class="muted company">{{ role.company }}</p>
      </div>
      <span class="period">{{ role.period }}</span>
    </div>

    <p class="muted">{{ role.location }}</p>

    <ul class="list-clean">
      <li v-for="point in role.points" :key="point">{{ point }}</li>
    </ul>
  </article>
</template>

<script setup>
defineProps({
  role: {
    type: Object,
    required: true,
  },
})
</script>

<style scoped>
.experience-card {
  padding: 14px;
}

.top-row {
  display: flex;
  justify-content: space-between;
  gap: 12px;
  align-items: start;
}

.top-row h3 {
  font-size: 0.92rem;
  line-height: 1.2;
}

.company,
.muted {
  font-size: 0.84rem;
}

.company {
  margin-bottom: 0;
}

.period {
  flex-shrink: 0;
  padding: 5px 9px;
  border-radius: 999px;
  background: rgba(31, 79, 145, 0.08);
  color: #23466e;
  font-size: 0.66rem;
  font-weight: 700;
}

@media (max-width: 720px) {
  .top-row {
    display: grid;
  }
}
</style>
