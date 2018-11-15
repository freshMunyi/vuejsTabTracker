<template>
  <div>
    <h1>Register</h1>
    <input 
    type="email" 
    name="email" 
    placeholder="Email"
    v-model="email" />

    <br/><br/>
    
    <input 
    type="password" 
    name="password" 
    placeholder="Password"
    v-model="password" />
    
    <br/><br/>
    
    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticaitonService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      email: 'abc@abc.com',
      password: 'abc123'
    }
  },
  methods:{
    async register() {
      const response = await AuthenticaitonService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data);
    }
  }
  // watch: {
  //   email(value) {
  //     console.log('email has changed', value)
  //   }
  // },
  // mounted() {
  //   setTimeout(() => {
  //     this.email = 'hello world'
  //   }, 2000)
  // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
