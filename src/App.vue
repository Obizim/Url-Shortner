<template>
  <div id="app">
    <AppNavigation />
    <router-view />
  </div>
</template>

<script>
import AppNavigation from "@/components/AppNavigation.vue";
export default {
  components: {
    AppNavigation
  }
};
</script>

<style lang="scss"></style>
