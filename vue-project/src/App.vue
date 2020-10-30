<template>
  <div id="app">
    <List />
      </div>
</template>

<script>
import List from './components/List'
export default {
  name: 'app',
  data () {
    return {
      Mainlist: undefined
    }
  },
  components: {
    List
  }

}
</script>

<style>

</style>
