# egyik módja, hogy elrejtsem a page-t v-if="data.length > 0"

<template>
  <navbar :pages="pages" :active-page="activePage" :nav-link-click="(index) => activePage = index"></navbar>
  <page-viewer v-if="pages.length > 0" :page="pages[activePage]"></page-viewer>
  <div v-show="false">Hide this content</div>
</template>

<script>
import Navbar from "./components/Navbar.vue"
import PageViewer from "./components/PageViewer.vue";

export default {
  components: {
    Navbar,
    PageViewer
  },
  created() {
    this.getPages()
  },
  data() {
    return {
      activePage: 0,
      pages: []
    }
  },
  methods: {
    async getPages() {
      let res = await fetch('pages.json')
      let data = await res.json()

      this.pages = data
    }
  }
}
</script>
