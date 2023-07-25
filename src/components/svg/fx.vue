<script>
const isHighlighted = (current, max) => {
  return current >= max - max / 2;
};

export default {
  data() {
    return {
      debounce: {
        current: 5,
        max: 5,
      },
      fx: {
        highlight: false,
      },
      position: {
        x: 0,
        y: 0,
      },
    };
  },
  mounted() {
    document.body.addEventListener('mousemove', this.onMouseMove);
  },
  beforeUnmount() {
    document.body.removeEventListener('mousemove', this.onMouseMove);
  },
  methods: {
    onMouseMove(event) {
      const debounce = this.debounce;

      debounce.current--;

      this.fx.highlight = isHighlighted(debounce.current, debounce.max);

      if (debounce.current > 0) {
        return;
      }

      const pos = this.position;
      pos.x = event.clientX;
      pos.y = event.clientY;

      debounce.current = debounce.max;
    },
  },
};
</script>

<template>
  <svg :class="fx.highlight ? 'fx-svg --active' : 'fx-svg'" width="400" height="400" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <radialGradient id="fx-gradient" cx="50%" cy="50%" r="50%" fx="50%" fy="50%">
        <stop offset="0%" style="stop-color: rgba(0, 255, 255, 0.5); stop-opacity: 1" />
        <stop offset="100%" style="stop-color: rgba(25, 255, 255, 0); stop-opacity: 0" />
      </radialGradient>
    </defs>
    <circle :cx="position.x" :cy="position.y" r="200" fill="url(#fx-gradient)" />
  </svg>
</template>

<style>
.fx-svg {
  pointer-events: none;
  position: absolute;
  top: 0;
  left: 0;
  display: block;
  width: 100vw;
  height: 100vh;
  opacity: 0.75;
  transition: filter 0.2s ease-in, opacity 0.3s ease-in;

  /* lighten|overlay|saturation|screen|soft-light */
  mix-blend-mode: saturation;
}

.fx-svg.--active {
  filter: saturate(1.6);
  opacity: 1;
}
</style>
