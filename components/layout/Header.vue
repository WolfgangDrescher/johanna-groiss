<template>
  <header class="layout-header">
    <div class="flex">
      <div class="flex-1">
        <nuxt-link to="/">
          Johanna Groiss
        </nuxt-link>
      </div>
      <div class="nav flex-1 flex justify-end">
        <nuxt-link class="nav-item" :to="{name: 'index'}">
          Über mich
        </nuxt-link>
        <nuxt-link class="nav-item" :to="{name: 'index'}">
          Angebot
        </nuxt-link>
      </div>
    </div>
  </header>
</template>

<style scoped lang="scss">
.layout-header {
  @apply fixed w-full top-0 px-16 py-10;
}

.nav .nav-item {
  margin-left: 2rem;
}

.nav .nuxt-link-exact-active {
  color: $primary;
}
</style>
