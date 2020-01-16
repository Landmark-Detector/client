<template>
  <div>
    <landingPage></landingPage>
  <div class="container-fluid vh-100 vw-100" id="user-page">
    <div class="row">
      <div class="col" :style="{'border-bottom': 'solid 1px black'}">
        <UploadBox @img="getImgUrl"></UploadBox>
        <UploadModal :imgUrl="imgUrl"></UploadModal>
      </div>
    </div>
  </div>
</template>

<script>
import landingPage from './components/landingPage'
import Vue from 'vue'
import UploadBox from "./UploadBox.vue";
import UploadModal from "./UploadModal.vue";

export default {
  components: {
    landingPage
  },
  data() {
    return {
      message: "Hello world",
      imgUrl: null
    };
  },
  methods: {
    getImgUrl(url) {
      this.imgUrl = url;
    }
  },
  components: {
    UploadBox,
    UploadModal
  }
};
</script>

<style scoped></style>
