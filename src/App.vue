<template>
  <div>
    <h1>Staima</h1>
    <input type="text" name="text" v-model="ticket.subject" /> <br> <br>
    <input type="text" name="text" v-model="ticket.body" /> <br /> <br>
    <button v-on:click="addUser()">Add New User</button>
  </div>
  
</template>

<script>
import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      ticket: {
        "subject": null,
        "body": null
      }
    
      
    };
  },
  methods: {
    async addUser() {
      let result =await axios.post(process.env.VUE_APP_WHATEVERYOUWANT, this.ticket);
      console.warn(result);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>