<template>
  <div>
    <landingPage></landingPage>
  <div class="container-fluid vh-100 vw-100" id="user-page">
    <div class="row">
      <div class="col" :style="{'border-bottom': 'solid 1px black'}">
        <upload-box @imgData="getImg"></upload-box>
        <upload-modal :imgData="images[images.length - 1]"></upload-modal>
      </div>
    </div>

    <div class="row">
      <div class="col" v-if="imgUrl">
        <b-card-group deck>
          <div v-for="image in images" :key="image.url">
            <history-card :img="image"></history-card>
          </div>
        </b-card-group>
      </div>
    </div>
  </div>
</template>

<script>
import landingPage from './components/landingPage'
import Vue from 'vue'
import UploadBox from "./UploadBox.vue";
import UploadModal from "./UploadModal.vue";
import HistoryCard from "./HistoryCard.vue";

export default {
  components: {
    landingPage
  },
  data() {
    return {
      message: "Hello world",
      imgUrl: null,
      images: []
    };
  },
  methods: {
    getImg(data) {
      this.imgUrl = data.url;
      this.images.push(data);
    },
    showLoading() {
      let timerInterval;
      Swal.fire({
        title: "Auto close alert!",
        html: "I will close in <b></b> milliseconds.",
        timer: 2000,
        timerProgressBar: true,
        onBeforeOpen: () => {
          Swal.showLoading();
          timerInterval = setInterval(() => {
            Swal.getContent().querySelector(
              "b"
            ).textContent = Swal.getTimerLeft();
          }, 100);
        },
        onClose: () => {
          clearInterval(timerInterval);
        }
      }).then(result => {
        if (
          /* Read more about handling dismissals below */
          result.dismiss === Swal.DismissReason.timer
        ) {
          console.log("I was closed by the timer"); // eslint-disable-line
        }
      });
    }
  },
  components: {
    UploadBox,
    UploadModal,
    HistoryCard
  }
};
</script>

<style scoped></style>
