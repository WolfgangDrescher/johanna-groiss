<template>
  <div class="stage">
    <layout-header />
    <main class="layout-main" :class="$route.name">
      <nuxt />
    </main>
    <layout-footer />
  </div>
</template>

<style scoped lang="scss">
.layout-main {
  @apply mt-24;
}
</style>
