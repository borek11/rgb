<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <button @click="met2">xxd</button>
  </div>
  
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import axios from "axios";

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  methods:{
    met(){
        axios.get("https://localhost:5001/identity/api/Account", {
          headers: {authorization: localStorage.getItem("token"),},
          })
          .then(
            (res) => {
              console.log(res);
            },
            (err) => {
              console.log(err);
            }
          );
    },
    met2(){
      this.$alert("Hello Vue Simple Alert.");
    }
  }
}

</script>

