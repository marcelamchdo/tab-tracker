<template>
  <div>
    <h1>Register</h1>

    <input type="email"
      name="email"
      v-model="email"
      placeholder="email" />
    <br>
    <input type="password"
      name="password"
      v-model="password"
      placeholder="password" />
    <br>
    <button
      @click="register">
      Register
    </button>
  </div>
</template>

<script>
import authenticationService from '@/services/authenticationService'

export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      await authenticationService.register({
        email: this.email,
        password: this.password
      })
    }
  }
}
</script>

<style scoped>
</style>
