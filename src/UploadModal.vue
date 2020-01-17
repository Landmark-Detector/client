<template>
  <div>
    <b-modal id="upload-image" hide-footer size="xl" class="modal-center">
      <template v-slot:modal-title>
        <b>Uploaded Image</b>
      </template>
      <div class="d-block text-center">
        <div class="row">
          <div class="col-9" v-if="imgData">
            <img
              :src="imgData.url"
              class="img-thumbnail img-fluid mx-auto d-block"
            />
          </div>
          <div class="col-3 text-left" v-if="imgData">
            <h3>{{ imgData.landmark.landmarkName }}</h3>
            <div v-if="imgData.landmark != 'Cant identify landmark'">
              <p>Location:</p>
              <ul>
                <li v-if="imgData.landmark.location">
                  longitude: {{ imgData.landmark.location.longitude }}
                </li>
                <li v-if="imgData.landmark.location">
                  latitude: {{ imgData.landmark.location.latitude }}
                </li>
              </ul>
              <p v-if="imgData.landmark">Score: {{ imgData.landmark.score }}</p>
            </div>
            <p>
              <share-button></share-button>
            </p>
          </div>
        </div>
      </div>
      <b-button
        class="mt-3 bg-outline-success"
        block
        @click="$bvModal.hide('upload-image')"
      >
        Well Done
      </b-button>
    </b-modal>
  </div>
</template>

<script>
import ShareButton from "./ShareButton.vue";

export default {
  props: ["imgData"],
  methods: {},
  watch: {
    imgData(val) {
      if (val) {
        this.imgUrl = val.url;
        this.$bvModal.show("upload-image");
      }
    }
  },
  components: {
    ShareButton
  }
};
</script>

<style scoped></style>
