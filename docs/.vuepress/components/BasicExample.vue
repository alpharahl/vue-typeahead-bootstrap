<template>
  <div >
    <link rel="stylesheet" href="../../../dist/VueBootstrapTypeahead.css">
    <VueBootstrapTypeahead
      v-model="query"
      :data="['Canada', 'United States', 'Mexico']"
      placeholder="Enter a country"
    />
    Selected Country: {{query}}
  </div>
</template>

<script>
  import 'bootstrap-vue/dist/bootstrap-vue.css'
  import VueBootstrapTypeahead from "../../../src/components/VueBootstrapTypeahead";
  export default {
    name: "demo",
    components: {VueBootstrapTypeahead},
    data(){
      return {
        query: null
      }
    }
  }
</script>

<style lang="scss">
  @import 'bootstrap/scss/bootstrap.scss';
</style>