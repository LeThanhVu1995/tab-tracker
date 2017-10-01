<template>
  <div>
  	<h1>Register</h1>
  	<input type="text" name="email" placeholder="email" v-model="email">
  	<input type="password" name="password" placeholder="password" v-model="password">
  	<button @click='register' >Register</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      email: 'abc',
      password: '123456'
    }
  },
  watch: {
    email (value) {
      console.log('emai has changed', value)
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  },
  mounted () {
    setTimeout(() => {
      this.email = 'hello world'
    }, 2000)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
