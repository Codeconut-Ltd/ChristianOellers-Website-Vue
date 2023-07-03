<script>
export default {
  data() {
    return {
      currentYear: new Date().getFullYear(),
      pages: {
        index: 'Home',
        legal: 'Imprint',
      },
    }
  },
  methods: {
    getCss(index) {
      const size = Object.keys(this.pages).length - 1;

      return (index < size ? 'border-end' : '')
    }
  },
}

</script>


<template>
  <footer class="mt-auto my-3 text-center">
    <p class="mr-3 pr-3 border-right">
      © 2019-{{ currentYear }} Codeconut Ltd. – All rights reserved.
    </p>
    <ul class="list-inline">
      <li v-for="(page, key, index) in pages" :key="key" :class="getCss(index) + ' list-inline-item px-3'">
        <a href="#" @click="$emit('page-change', key)">
          {{ page }}
        </a>
      </li>
    </ul>
  </footer>
</template>


<style>
a {
  text-decoration: none;
}

a:hover {
  color: var(--co-link-state);
}
</style>
