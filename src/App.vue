<template>
  <div>
    <div id="nav">
      <router-link :to="{name: 'Home'}">Home</router-link> |
      <router-link :to="{name: 'About'}">About</router-link> |
      <router-link :to="{name: 'Jobs'}">Jobs</router-link>
    </div>
    <router-view />
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
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
