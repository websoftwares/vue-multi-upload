<template>
<table>
  <th><td>ID</td></th>
  <th><td>Document</td></th>
  <tr v-for="document in documents"  v-bind:document="document" :key="document.id"  v-if="documents && documents.length">
    <td >{{document.id}}</td>
    <td >{{document.filename}}</td>
  </tr>
  <tr v-for="error of errors" v-if="errors && errors.length">
    <td >{{error}}</td>
  </tr>
</table>
</template>

<script>
import axios from 'axios'

export default {
  data () {
    return {
      documents: [],
      errors: []
    }
  },

  async created () {
    try {
      const response = await axios.get(`http://localhost:8080`)
      this.documents = response.data
    } catch (e) {
      this.errors.push(e)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
