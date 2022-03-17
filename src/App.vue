<template>
  <nav>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
  </nav>
  <router-view />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  widows: 100%;
  background-color: #2c3e50;
  padding: 30px;
}

nav a {
  font-size: 24px;
  line-height: 30px;
  letter-spacing: 0.05rem;
  font-weight: bold;
  text-decoration: none;
  color: #fff;
  padding-right: 30px;
}

nav a.router-link-exact-active {
  color: #42b983;
}

.home .form-input {
  font-size: 20px;
  line-height: 30px;
  letter-spacing: 0.05rem;
  padding: 20px;
  border: 1px solid #2c3e50;
}

.home .pokes {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  padding-top: 50px;
}

.home .pokes span {
  font-size: 18px;
  line-height: 30px;
  font-weight: 500;
  letter-spacing: 0.05rem;
  padding: 30px 40px;
}
</style>
