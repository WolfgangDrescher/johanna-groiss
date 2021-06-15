<template>
  <span v-if="!to">
    <slot />
  </span>

  <a
    v-else-if="typeof to === 'string' && isAnchor(to)"
    v-scroll-to="isAnchor(to)"
    :href="isAnchor(to)"
    class="cursor-pointer"
  >
    <slot />
  </a>

  <a v-else-if="typeof to === 'string' && to.startsWith('http')" :href="to" rel="nofollow noopener">
    <slot />
  </a>

  <a v-else-if="typeof to === 'string' && (to.startsWith('tel:') || to.startsWith('mailto:'))" href="#" @click.prevent="special(to)">
    <slot />
  </a>

  <nuxt-link v-else :to="to">
    <slot />
  </nuxt-link>
</template>

<script>
export default {
  props: {
    to: {
      type: [String, Object],
      default: null,
    },
  },
  methods: {
    isAnchor (to) {
      if (to.startsWith('#')) {
        return to;
      }
      return false;
    },
    special (to) {
      window.location.href = to.replace(/ /g, '');
    },
  },
};
</script>
