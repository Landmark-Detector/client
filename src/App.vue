<template>
  <div>
    <landingPage></landingPage>
  </div>  
</template>

<script>
import landingPage from './components/landingPage'
import Vue from 'vue'

export default {
  components: {
    landingPage
  },
  data() {
    return {
      message: 'Hello world'
    }
  }
}
</script>

<style scoped></style>
