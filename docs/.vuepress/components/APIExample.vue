<template>
  <div>
    <VueBootstrapTypeahead
      :data="users"
      :serializer="item => item.login"
      v-model="query"
      @input="getUsersFromGithub(query)"
      @hit="selectedUser = $event"
      placeholder="Search Github Users"
    />
    Selected User: <span v-if="selectedUser">{{selectedUser.login}}</span>
  </div>

</template>

<script>
  import 'bootstrap-vue/dist/bootstrap-vue.css'
  import VueBootstrapTypeahead from "../../../src/components/VueBootstrapTypeahead";
  import {debounce} from 'lodash';

  export default {
    name: "APIExample",
    components: {VueBootstrapTypeahead},
    data(){
      return {
        query: '',
        selectedUser: null,
        users: []
      }
    },

    methods: {
      getUsersFromGithub: debounce(function(query){
        fetch(`https://api.github.com/search/users?q=${query}`)
        .then((res) => {
          return res.json();
        })
        .then((data) => {
          this.users = data.items
        })
      }, 1000)
    }
  }
</script>

<style lang="scss">
  @import 'bootstrap/scss/bootstrap.scss';
</style>