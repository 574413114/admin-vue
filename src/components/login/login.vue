<template>
  <div>
      <p>登陆组件</p>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data () {
    return {
      userForm: {
        username: '',
        password: ''
      }
    }
  },
  methods: {
    async login () {
      const res = await axios.post('http://localhost:8888/api/private/v1/login', this.userForm)
      const data = res.data
      if (data.meta.status === 200) {
        this.$router.push({
          name: 'home'
        })
      }
    }
  }
}
</script>

<style>

</style>
