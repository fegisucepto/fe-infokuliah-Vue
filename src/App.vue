<template>
  <div id="app">
    <!-- <nav> -->
      <!-- <router-link to="/">Home</router-link> | -->
      <!-- <router-link to="/Couses">Couses</router-link> -->
    <!-- </nav> -->
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  metaInfo: {
    // if no subcomponents specify a metaInfo.title, this title will be used
    title: 'Kursus Persiapan Masuk PTN',
    // all titles will be injected into this template
    titleTemplate: '%s | Infokuliah.id'
  }
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

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
