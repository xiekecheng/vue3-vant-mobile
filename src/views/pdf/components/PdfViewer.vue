<script>
import VuePdfEmbed from 'vue-pdf-embed'
// OR THE FOLLOWING IMPORT FOR VUE 2
// import VuePdfEmbed from 'vue-pdf-embed/dist/vue2-pdf-embed'

export default {
  components: {
    VuePdfEmbed,
  },
  data() {
    return {
      isLoading: true,
      page: null,
      pageCount: 1,
      // pdfSource:
      //   'https://raw.githubusercontent.com/mozilla/pdf.js/ba2edeae/web/compressed.tracemonkey-pldi-09.pdf',
      pdfSource:
        '/p001.pdf',
      showAllPages: true,
    }
  },
  // watch: {
  //   showAllPages() {
  //     this.page = this.showAllPages ? null : 1
  //   }
  // },
  methods: {
    handleDocumentRender(args) {
      console.log(args)
      this.isLoading = false
      this.pageCount = this.$refs.pdfRef.pageCount
    },
    handlePasswordRequest(callback, retry) {
      callback(prompt(retry ? 'Enter password again' : 'Enter password'))
    },
  },
}
</script>

<template>
  <div class="app-content">
    <VuePdfEmbed
      ref="pdfRef"
      :source="pdfSource"
      :page="page"
      @password-requested="handlePasswordRequest"
      @rendered="handleDocumentRender"
    />
  </div>
</template>
