<template>
  <div>
    <chart></chart>
  </div>

</template>

<script>
  import Chart from "./components/Chart";
export default {
  name: 'app',
    components:{Chart,},
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style>
</style>
