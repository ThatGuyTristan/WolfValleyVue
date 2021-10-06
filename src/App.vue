<template lang="pug">
  v-app
    v-main
      div
        v-text-field(v-model="email" label="E-Mail")
        v-text-field(type="password" label="Password" v-model="password")
        v-btn(@click="login") Login
</template>

<script>
import axios from "axios"

export default {
  name: 'App',
  data: () => ({
    password: null,
    email: null
    //
  }),
  methods: {
    login(){
      axios.post("localhost:3000/sessions/create", { email: this.email, password: this.password }).then().catch(err => console.log(err))
    }
  }
};
</script>
