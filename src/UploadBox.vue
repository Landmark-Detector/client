<template>
  <div>
    <div class="row my-3 justify-content-center">
      <div class="col-md-6">
        <b-form-file
          accept="image/jpeg, image/png, image/gif"
          ref="file-input"
          v-model="file"
          :state="Boolean(file)"
          placeholder="Choose a file or drop it here..."
          @change.prevent="onFileChange"
          drop-placeholder="Drop file here..."
          size="lg"
          enctype="multipart/form-data"
        ></b-form-file>
      </div>
    </div>
  </div>
</template>

<script>
import api from "./api.js";
import axios from "axios";

export default {
  data() {
    return {
      file: null,
      url: null,
      modalShow: false
    };
  },
  methods: {
    onFileChange(e) {
      const tempFile = event.target.files[0];
      this.url = URL.createObjectURL(tempFile);

      let sendData = new FormData();
      sendData.append("file", tempFile);
      axios
        .post("http://35.240.152.89/upload/image", sendData)
        .then(({data}) => {
          // this.$refs["file-input"].reset();
          this.$emit("imgData", data);
        })
        .catch(err => {
          console.log(err);
        });
    },
    onDrop(e) {
      const file = e.dataTransfer.files[0];

      // Do something with the dropped file
      console.log(file);
    }
  }
};
</script>

<style scoped></style>
