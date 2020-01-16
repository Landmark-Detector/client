<template> </template>

<script>
export default {
  props: ["imgUrl"],
  methods: {
    showMsgOk() {
      const h = this.$createElement;
      // Using HTML string
      const titleVNode = h("div", {
        domProps: {innerHTML: "<b>Uploaded Image</b>"}
      });
      // More complex structure
      const messageVNode = h("div", {class: [""]}, [
        // h('p', { class: ['text-center'] }, [
        //   ' Flashy ',
        //   h('strong', {}, 'msgBoxOk'),
        //   ' message ',
        // ]),
        // h('p', { class: ['text-center'] }, [h('b-spinner')]),
        h("b-img", {
          props: {
            src: this.imgUrl,
            thumbnail: true,
            center: true,
            fluid: true
          }
        })
      ]);
      // We must pass the generated VNodes as arrays
      this.$bvModal.msgBoxOk([messageVNode], {
        title: [titleVNode],
        buttonSize: "sm",
        centered: true,
        size: "xl"
      });
    }
  },
  watch: {
    imgUrl(val) {
      if (val) {
        this.showMsgOk();
      }
    }
  }
};
</script>

<style scoped></style>
