<script>
import PortfolioViewsLinks from './views/Links'

export default {
  components: {
    PortfolioViewsLinks,
  },
  data() {
    return {
      categories: {
        Business: [
          { key: 0, name: 'LinkedIn', url: 'https://www.linkedin.com/in/TheRemoteCoder' },
          { key: 1, name: 'Xing', url: 'https://www.xing.com/profile/Christian_Oellers2' },
        ],
        Code: [
          { key: 10, name: 'GitHub', url: 'https://github.com/ChristianOellers' },
          { key: 11, name: 'StackOverflow', url: 'https://stackoverflow.com/users/1045692/theremotecoder' },
        ],
        Design: [
          { key: 20, name: 'Behance', url: 'https://www.behance.net/DrawfulMind' },
          { key: 21, name: 'Dribbble', url: 'https://dribbble.com/DrawfulMind' },
          { key: 22, name: 'ArtStation', url: 'https://www.artstation.com/drawfulmind' },
        ],
      }
    }
  }
}
</script>


<template>
  <section class="row justify-content-left justify-content-md-center text-center text-sm-start">
    <div v-for="(items, category) in categories" :key="category" class="col-12 col-sm-auto offset-sm-1">
      <h4 class="h5">{{ category }}</h4>
      <PortfolioViewsLinks :items="items" />
    </div>
  </section>
</template>
