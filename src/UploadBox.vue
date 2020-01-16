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
          @dragover.prevent
          @drop.stop.prevent="onDrop"
          size="lg"
        ></b-form-file>
      </div>
    </div>
  </div>
</template>

<script>
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
      const tempFile = e.target.files[0];
      this.url = URL.createObjectURL(tempFile);
      // this.$refs["file-input"].reset();
      this.$emit("img", this.url);
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
