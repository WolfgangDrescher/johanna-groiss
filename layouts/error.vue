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
  layout: 'error',
  props: {
    error: {
      type: Object,
      default: () => {},
    },
  },
  head () {
    return {
      title: `[${this.error.statusCode}] ${this.error.message}`,
    };
  },
  created () {
    console.log(this.error);
  },
};
</script>
