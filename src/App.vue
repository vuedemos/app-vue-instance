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
  },
  beforeCreate () {
    console.log(`>>> ==== 钩子函数 beforeCreate ==== >>>`)
    console.log(`this.message: ${this.message}`)
    console.log(`this.$el: ${this.$el}`)
    console.log(`>>> ==== End ==== >>>`)
  },
  created () {
      console.log(`>>> ==== 钩子函数 created ==== >>>`)
      console.log(`this.message: ${this.message}`)
      console.log(`this.$el: ${this.$el}`)
      console.log(`>>> ==== End ==== >>>`)
  },
  beforeMount () {
    console.log(`>>> |_==_| 钩子函数 beforeMount |_==_| >>>`)
    console.log(`this.message: ${this.message}`)
    console.log(`this.$el: ${this.$el}`)
    console.log(`>> |_==_| this.$el.outerHTML 开始 |_==_| >>`)
    console.log(this.$el.outerHTML)
    console.log(`>> |_==_| this.$el.outerHTML 结束 |_==_|`)
    console.log(`>>> |_==_| End |_==_| >>>`)
  },
  mounted () {
      console.log(`>>> |_==_| 钩子函数 mounted |_==_| >>>`)
      console.log(`this.message: ${this.message}`)
      console.log(`this.$el: ${this.$el}`)
      console.log(`>> |_==_| this.$el.outerHTML 开始 |_==_| >>`)
      console.log(this.$el.outerHTML)
      console.log(`>> |_==_| this.$el.outerHTML 结束 |_==_| >>`)
      console.log(`>>> |_==_| End |_==_| >>>`)
  },
  beforeUpdate () {
    console.log(`>>> (^_^) 钩子函数 beforeUpdate (^_^) >>>`)
    console.log(`this.message: ${this.message}`)
    console.log(`this.$el: ${this.$el}`)
    console.log(this.$el.outerHTML)
    console.log(`>>> (^_^) End (^_^) >>>`)
  },
  updated () {
      console.log(`>>> (^_^) 钩子函数 updated (^_^) >>>`)
      console.log(`this.message: ${this.message}`)
      console.log(`this.$el: ${this.$el}`)
      console.log(this.$el.outerHTML)
      console.log(`>>> (^_^) End (^_^) >>>`)
  },
  beforeDestroy () {
    console.log(`(^_^) 钩子函数 beforeDestroy (^_^)`)
    console.log(`this.message: ${this.message}`)
    console.log(`this.$el:${this.$el}`)
    console.log(this.$el.outerHTML)
    console.log(`(^_^) End (^_^)`)
  },
  destroyed () {
      console.log(`(^_^) 钩子函数 destroyed (^_^)`)
      console.log(`this.message: ${this.message}`)
      console.log(`this.$el:${this.$el}`)
      console.log(this.$el.outerHTML)
      console.log(`(^_^) End (^_^)`)
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
