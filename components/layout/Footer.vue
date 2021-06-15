<template>
  <footer class="layout-footer">
    <container>
      <div class="flex my-5">
        <div class="flex-1">
          Johanna Groiss
        </div>
        <div class="layout-footer-nav flex-1 flex justify-end">
          <nuxt-link :to="{name: 'agb'}">
            AGB
          </nuxt-link>
          <nuxt-link :to="{name: 'datenschutz'}">
            Datenschutz
          </nuxt-link>
        </div>
      </div>
    </container>
  </footer>
</template>

<style scoped lang="scss">
.layout-footer {
  background-color: $primary;
  color: white;
}

.layout-footer-nav {
  a {
    @apply ml-3;
  }
}
</style>
