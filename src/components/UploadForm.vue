<template>
  <form action="upload" ref="upload" id="upload" enctype="multipart/form-data">
    <input type="file" name="files[]" multiple><br />
    <input type="submit">
</form>
</template>

<script>
  export default {
    mounted () {
      let form = this.$refs.upload
      form.addEventListener('submit', async (e) => {
        e.preventDefault()
        let formdata = new FormData(form)

        try {
          await fetch('http://localhost:8080/upload.php', {method: 'POST', body: formdata})
          window.location.reload(false)
        } catch (error) {
          console.error(error)
        }
      })
    }
  }
</script>

<style scoped>
</style>
