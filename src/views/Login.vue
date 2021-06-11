<template>
  <Notification v-bind:text="text" v-if="notification" />
  <form @submit.prevent="login">
    <div class="field">
      <label class="label">Email</label>
      <div class="control">
        <input class="input" type="email" v-model="email" placeholder="Email" />
      </div>
    </div>

    <div class="field">
      <label class="label">Password</label>
      <div class="control">
        <input class="input" type="password" v-model="password" placeholder="Password" />
      </div>
    </div>

    <button class="button is-primary" type="submit">Submit</button>
  </form>
</template>

<script>
import axios from 'axios';
import Notification from '../components/Notification.vue';

export default {
  name: 'Login',
  components: { Notification },
  data() {
    return {
      email: '',
      password: '',
      text: '',
      notification: false,
    };
  },
  methods: {
    login() {
      axios
        .post('https://plankink-server-2jcan.ondigitalocean.app/v1/auth/login', {
          email: this.email,
          password: this.password,
        })
        .then((res) => {
          this.notification = true;
          this.text = res.data.msg;
          localStorage.setItem('token', res.data.token);
        });
    },
  },
};
</script>

<style></style>
