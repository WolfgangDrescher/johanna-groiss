<template>
  <container>
    <heading>Projektübersicht</heading>
    <layout-section>
      <div v-for="project in projects" :key="project.slug">
        {{ project.slug }}
        <h2>{{ project.date }}</h2>
        <nuxt-content :document="project" />
      </div>
    </layout-section>
    <layout-section>
      <p>
        Hier Kontakt aufnehmen
      </p>
    </layout-section>
  </container>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const projects = await $content('projects').where({
      active: true,
    }).fetch();
    return {
      projects,
    };
  },
};
</script>
