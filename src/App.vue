<script>
import store from './store' // import 我们刚刚创建的 store
import { mapActions, mapGetters } from 'vuex'

export default {
  render(h) {
    return (
      <div id="app">
        <display></display>
        <increment></increment>
      </div>
    )
  },
  name: 'app',
  components: {
    Display: {
      render(h) {
        return <h1>Count is {this.count}</h1>
      },
      computed: mapGetters([
        'count'
      ])
    },
    Increment: {
      render(h) {
        return <button on-click={this.INCREMENT}>Increment +1</button>
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
