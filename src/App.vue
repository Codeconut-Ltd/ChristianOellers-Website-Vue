<script>
/* eslint-disable no-unused-vars */

import 'bootstrap/dist/css/bootstrap.css'
import './assets/vendor.css'
import './assets/vars.css'
import './assets/content/elements.css'
import './assets/content/layout.css'

import PageIndex from './components/Index'
import PageLegal from './components/Legal'
import MenuFooter from './components/menu/Footer'
import MenuHeader from './components/menu/Header'
import SvgFx from './components/svg/fx'

export default {
  components: {
    MenuFooter,
    MenuHeader,
    PageIndex,
    PageLegal,
    SvgFx,
  },
  methods: {
    setPage(page) {
      this.page = page
    }
  },
  data() {
    return {
      page: 'index', // index|legal
    }
  }
}
</script>


<template>
  <div v-if="page == 'legal'">
    <MenuHeader />
    <PageLegal />
    <MenuFooter :page="page" @page-change="setPage" />
  </div>
  <div v-else>
    <MenuHeader />
    <PageIndex />
    <MenuFooter :page="page" @page-change="setPage" />
    <SvgFx />
  </div>
</template>


<style>
#app {
  font-family: system-ui, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
