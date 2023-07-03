<script>
import PortfolioViewsVentures from './views/Ventures'

export default {
  components: {
    PortfolioViewsVentures,
  },
  data() {
    return {
      categories: [
        {
          key: 0,
          css: 'codeconut',
          name: 'Codeconut',
          url: 'https://www.codeconut.io/',
        },
        {
          key: 1,
          css: 'drawfulmind',
          name: 'DrawfulMind',
          url: 'https://www.drawfulmind.com/',
        },
        {
          key: 2,
          css: 'theremotecoder',
          name: 'TheRemoteCoder',
          url: 'https://www.theremotecoder.com/',
        },
        {
          key: 3,
          css: 'itsajourneything',
          name: 'It\'s a Journey Thing',
          url: 'https://www.itsajourneything.com/',
        },
      ]
    }
  }
}
</script>


<template>
  <div class="co-tiles container-fluid px-0 py-5">
    <div class="row align-items-center">
      <PortfolioViewsVentures v-for="(item) in categories" :key="item.key" :item="item" />
    </div>
  </div>
</template>


<style>
.co-tiles {
  transform: scale(1);
  transition: transform 0.25s ease-out;
}

@media (min-width: 1280px) {
  .co-tiles {
    transform: scale(1.15);
  }
}

@media (min-width: 1920px) {
  .co-tiles {
    transform: scale(1.25);
  }
}
</style>
