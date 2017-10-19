<template>
  <div id="app">
    <img src="./assets/logo.png">
    <nav class="navbar navbar-toggleable-md navbar-light bg-faded">
      <a class="navbar-brand" href="#">Navbar</a>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">

          <li class="nav-item active">
            <router-link :to="'/'" class="nav-link">Hello1</router-link>
          </li>

          <li class="nav-item">
            <router-link :to= "'/hello2'" class="nav-link" >Hello2</router-link>
          </li>


        </ul>
      </div>
    </nav>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style lang="scss">
  @import "~bootstrap/scss/bootstrap";
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
