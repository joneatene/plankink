<template>
  <Navigation />
  <section class="section">
    <div class="container">
      <router-view />
    </div>
  </section>
</template>

<script>
import Navigation from './components/Navigation.vue';

export default {
  name: 'App',
  components: { Navigation },
};
</script>

<style></style>
