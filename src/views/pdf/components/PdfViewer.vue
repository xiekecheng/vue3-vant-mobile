<script>
import VuePdfEmbed from 'vue-pdf-embed';

// OR THE FOLLOWING IMPORT FOR VUE 2
// import VuePdfEmbed from 'vue-pdf-embed/dist/vue2-pdf-embed'

export default {
  components: {
    VuePdfEmbed,
  },
  data() {
    return {
      // isLoading: true,
      page: null,
      // pageCount: 1,
      // pdfSource:
      //   'https://raw.githubusercontent.com/mozilla/pdf.js/ba2edeae/web/compressed.tracemonkey-pldi-09.pdf',
      pdfSource:
        'https://goldhosedev.s3.ap-east-1.amazonaws.com/openapitmp/06/bf/Fixed%20Coupon%20Note%20with%20Knock-In%20Feature_CSB%20Indicative%20TS_template.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20231220T011516Z&X-Amz-SignedHeaders=host&X-Amz-Expires=86400&X-Amz-Credential=AKIAV3DWDIQ4V2YBVFVW%2F20231220%2Fap-east-1%2Fs3%2Faws4_request&X-Amz-Signature=14f6ecb79eb9928f1b659cf7aa1bcfbc6cd171dabc16953dae23bbe1b5c8e692',
    }
  },
  mounted() {
    // axios.get('https://goldhosedev.s3.ap-east-1.amazonaws.com/openapitmp/06/bf/Fixed%20Coupon%20Note%20with%20Knock-In%20Feature_CSB%20Indicative%20TS_template.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20231220T011516Z&X-Amz-SignedHeaders=host&X-Amz-Expires=86400&X-Amz-Credential=AKIAV3DWDIQ4V2YBVFVW%2F20231220%2Fap-east-1%2Fs3%2Faws4_request&X-Amz-Signature=14f6ecb79eb9928f1b659cf7aa1bcfbc6cd171dabc16953dae23bbe1b5c8e692').then((res) => {
    //   console.log(res)
    // })

  // methods: {
  //   handleDocumentRender(args) {
  //     console.log(args)
  //     this.isLoading = false
  //     this.pageCount = this.$refs.pdfRef.pageCount
  //   },
  //   handlePasswordRequest(callback, retry) {
  //     callback(prompt(retry ? 'Enter password again' : 'Enter password'))
  //   },
  },
}
</script>

<!--

      @password-requested="handlePasswordRequest"
      @rendered="handleDocumentRender"

 -->

<template>
  <div class="app-content">
    <VuePdfEmbed
      ref="pdfRef"
      :source="pdfSource"
      :page="page"
    />
  </div>
</template>
