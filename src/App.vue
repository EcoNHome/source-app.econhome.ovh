<template>
  <div id="app">
      <nav class="col-md-2 d-none d-md-block bg-light sidebar">
          <div class="sidebar-sticky">
              <ul class="nav flex-column">
                  <li class="nav-item">
                      <router-link class="nav-link" to="/">Accueil</router-link>
                  </li>
                  <li class="nav-item">
                      <router-link class="nav-link" to="/about">About</router-link>
                  </li>
                  <li class="nav-item">
                      <router-link class="nav-link" to="/pouet">Pouet</router-link>
                  </li>
              </ul>
          </div>
      </nav>
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
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
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
