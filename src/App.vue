<template>
  <div id="app">
    <DocumentsList/>
    <UploadForm />
  </div>
</template>

<script>
import DocumentsList from './components/DocumentsList'
import UploadForm from './components/UploadForm'

export default {
  name: 'app',
  components: {
    DocumentsList, UploadForm
  }
}
</script>

<style>
</style>
