<template>
  <div class="notification">
    <button class="delete"></button>
    <p>{{ text }}</p>
  </div>
</template>

<script>
export default {
  name: 'Notification',
  props: ['text'],
};
</script>

<style></style>
