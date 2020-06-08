<template>
  <div id="app">
    <div id="nav">
      <h1 class="nav__title">Find History Events</h1>
      <div>
      <router-link :to="{name: 'Page1'}">Page1</router-link>
      <router-link :to="{name: 'Page2'}">Page2</router-link>
      </div>
    </div>
    <router-view/>
  </div>
</template>

<style lang="scss">
#app {
  margin: 0;
  padding: 0;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2a3b4e;
}

.nav__title{
    color: #f4fffa;
}

#nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 30px;
  background-color: #0bac66;

  a {
    font-weight: bold;
    color: #2c3e50;
    text-decoration: none;
    margin-left: 10px;
    font-size: 24px;

    &.router-link-exact-active {
      color: #f4fffa;
    }
  }
}
</style>
