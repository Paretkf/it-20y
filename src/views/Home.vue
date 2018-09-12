<template>
  <div class="home">
    <button @click="login()"> Login </button>
    <div v-if="user.user">
       <img :src="user.user.photoURL" alt=""> <br>
      {{user.user.displayName}} <br>
      <button @click="logout()"> Logout </button>
    </div>
   
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import { mapActions, mapState } from 'vuex'
export default {
  name: 'home',
  components: {
    HelloWorld
  },
  methods: {
    ...mapActions({
      login: 'login',
      logout: 'logout'
    })
  },
  computed: {
    ...mapState({
      user: state => state.user
    })
  }
}
</script>
