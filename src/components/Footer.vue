<script>
export default {
  name: "Component",
  data() {
    return {
      Settings: window.Settings,
      localStorage: localStorage,
    };
  },
  async created() {
    document.title = (this.Settings.website || {}).title;
  },
};
</script>
<template>
  <main class="" v-if="Settings"></main>
</template>
