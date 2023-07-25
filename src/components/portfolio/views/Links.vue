<script>
export default {
  props: {
    items: {
      type: Object,
      required: true,
    },
  },
};
</script>

<template>
  <ul class="list list-unstyled mb-4">
    <li v-for="(item, category) in items" :key="category" class="co-link list list-unstyled my-1">
      <a :href="item.url" class="d-block d-sm-inline p-2 p-sm-0" target="_blank" rel="nofollow noopener noreferrer">{{ item.name }}</a>
    </li>
  </ul>
</template>
