<template>
  <nav class="navbar" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <router-link class="navbar-item" to="/">
        <h2 class="title">Plankink</h2>
      </router-link>

      <a
        role="button"
        class="navbar-burger"
        aria-label="menu"
        aria-expanded="false"
        data-target="navbarBasicExample"
      >
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>

    <div id="navbarBasicExample" class="navbar-menu">
      <div class="navbar-start">
        <router-link class="navbar-item" to="/">
          Home
        </router-link>

        <router-link class="navbar-item" to="/about">
          About
        </router-link>
      </div>

      <div class="navbar-end">
        <div class="navbar-item">
          <div class="buttons">
            <router-link class="button is-primary" to="/register" v-if="token" v-on:click="logout">
              <strong>Sign out</strong>
            </router-link>
            <div v-else>
              <router-link class="button is-primary" to="/register">
                <strong>Sign up</strong>
              </router-link>
              <router-link class="button is-light" to="/login">
                Log in
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navigation',
  data() {
    return { token: '' };
  },
  beforeMount() {
    this.token = localStorage.getItem('token');
  },
  beforeUpdate() {
    this.token = localStorage.getItem('token');
  },
  methods: {
    logout() {
      localStorage.removeItem('token');
    },
  },
};
</script>

<style></style>
