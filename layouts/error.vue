<template>
  <container>
    <template v-if="error.statusCode === 404">
      Seite nicht gefunden
    </template>
    <template v-else>
      Oops! Ein Fehler ist aufgetreten
    </template>
  </container>
</template>

<script>
export default {
  props: {
    error: {
      type: Object,
      default: () => {},
    },
  },
  layout: 'error',
  created () {
    console.log(this.error);
  },
  head () {
    return {
      title: `[${this.error.statusCode}] ${this.error.message}`,
    };
  },
};
</script>
