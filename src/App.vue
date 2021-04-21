<template>
  <div>
    <div id="nav">
      <router-link :to="{ name: 'Home' }">Home</router-link> |
      <router-link :to="{ name: 'About' }">About</router-link> |
      <router-link :to="{ name: 'Jobs' }">Jobs</router-link>
    </div>

    <div class="buttonContainer">
      <!-- redirect -->
      <button @click="redirect">&#8734;</button>
      <!-- back -->
      <button @click="back">&#8592;</button>
      <!-- forward -->
      <button @click="forward">&#8594;</button>
    </div>

    <router-view />
  </div>
</template>


<script>
export default {
  methods: {
    redirect() {
      this.$router.push({ name: 'Home'})
    },
    back() {
      // -1 means go back, like going backwards in a index
      this.$router.go(-1)
    },
    forward() {
      this.$router.go(1)
    },
  },
}
</script>



<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.buttonContainer button{
  margin: 0 10px;
  padding: 10px;
  border: none;
  border-radius: 4px;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
}

#nav a.router-link-exact-active {
  color: white;
  background: royalblue;
  padding: 10px 5px;
  border-radius: 5px;
}
</style>
