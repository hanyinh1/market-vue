<template>
  <div>
    <li v-for="(item, index) of users" :key="index">{{item}}</li>
  </div>
</template>

<script>
export default {
  data () {
    return {
      users: []
    }
  },
  created () {
    this.axios.get('/localhost/user/getUserList')
      .then(res => {
        this.users = res.data
      })
      .catch(err => {
        console.log(err)
      })
  }
}
</script>

<style scoped>
</style>
