<template>
  <div id="app">
    <Display></Display>
    <Increment></Increment>
  </div>
</template>

<script>
import store from './store' // import 我们刚刚创建的 store
import { mapActions, mapGetters } from 'vuex'

export default {
  name: 'app',
  components: {
    Display: {
      render(h) {
        return h('h1', ['Count is ' + this.count])
      },
      computed: mapGetters([
        'count'
      ])
    },
    Increment: {
      render(h) {
        return h('button', {
          on: {
            click: this.INCREMENT
          }
        }, 'Increment +1')
      },
      methods: mapActions([
        'INCREMENT'
      ])
    }
  },
  store // 在根组件加入 store，让它的子组件和 store 连接
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
</style>
