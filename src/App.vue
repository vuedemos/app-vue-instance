<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h2>{{ message }}</h2>
    <div>
      <button @click="getRemoteMessage">获取远程数据</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      message: 'W3cplus.com'
    }
  },
  methods: {
    getRemoteMessage () {
      Promise.resolve('获取远程数据：大漠')
        .then((res) => {
          this.message = res
        })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button {
  margin: 10px;
  padding: 5px 15px;
  text-align: center;
  font-size: 1.2rem;
  transition: 0.5s;
  background-size: 200% auto;
  color: white;
  text-shadow: 0px 0px 10px rgba(0,0,0,0.2);
  box-shadow: 0 0 20px #eee;
  border-radius: 6px;
  background-image: linear-gradient(to right, #d75bb4 0%, #779bd7 51%, #ce229e 100%);
  cursor: pointer;
}
button:hover {
  background-position: right center;
}
button:active,
button:focus {
  outline: none;
}
</style>
