<template>
  <router-link to="/" class="title">Pokes Picker</router-link>
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

#app .title {
  font-size: 60px;
  line-height: 80px;
  font-weight: 700;
  letter-spacing: 0.08rem;
  text-decoration: none;
  color: #2c3e50;
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

.about {
  display: block;
  width: 30%;
  background-color: cadetblue;
  padding: 20px;
  margin: auto;
}

.about .pictures {
  display: flex;
  justify-content: center;
}

.about .pictures img {
  width: 100px;
}
</style>
