<script>
import svgbrandcodeconut from '../../svg/logos/codeconut';
import svgbranddrawfulmind from '../../svg/logos/drawfulmind';
import svgbranditsajourneything from '../../svg/logos/its-a-journey-thing';
import svgbrandtheremotecoder from '../../svg/logos/the-remote-coder';

export default {
  components: {
    svgbrandcodeconut,
    svgbranddrawfulmind,
    svgbranditsajourneything,
    svgbrandtheremotecoder,
  },
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  methods: {
    getSvgName(cssKey) {
      return `svgbrand${cssKey}`;
    },
  },
};
</script>

<template>
  <div class="col-12 col-sm-6 col-lg-3 px-sm-2 my-1 my-sm-2">
    <a
      :href="item.url"
      target="_blank"
      rel="nofollow noopener noreferrer"
      :class="'-' + item.css + ' d-flex justify-content-center align-items-center'"
    >
      <span class="visually-hidden">{{ item.name }}</span>
      <component class="mb-5 mb-sm-0" :is="getSvgName(item.css)" />
    </a>
  </div>
</template>

<style>
.co-svg-brand {
  color: var(--co-link);
  display: block;
  width: 65%;
  height: auto;
  transition: color 0.35s ease-out, transform 2s ease-out;
}

.co-svg-brand:hover {
  color: var(--co-link-state);
  transform: scale(1.05);
}

.-itsajourneything {
  position: relative;
  top: -10px;
}
</style>
