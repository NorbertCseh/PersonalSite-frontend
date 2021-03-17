<template>
  <div class="container">
    <div class="user" v-for="(user, _id) in users" :key="_id">
      Name: {{ user.name }} Email: {{ user.email }} Avatar:
      <img :src="user.avatar" height="50px" width="50px" />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data() {
    return {
      users: JSON,
    }
  },
  mounted() {
    this.$axios
      .get('https://norbertcseh-site.herokuapp.com/api/user/users')
      .then((res) => {
        this.users = res.data.msg as JSON
      })
  },
})
</script>

<style>
.conatiner {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>