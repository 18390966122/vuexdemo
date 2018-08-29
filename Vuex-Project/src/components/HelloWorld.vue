<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
      <input type="text" v-model="inputNum" style="width: 200px;height: 30px;">
  </div>
</template>

<script>
import { mapMutations, mapGetters } from 'vuex'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      inputNum: 0
    }
  },
  created() {
    this.inputNum = this.num
  },
  computed: {
    ...mapGetters(['num'])
  },
  watch: {
    inputNum (newVal) {
      this.SET_NUM(newVal)
    }
  },
  methods: {
    ...mapMutations(['SET_NUM'])
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
