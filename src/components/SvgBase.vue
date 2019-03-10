<template>
  <svg
    xmlns="http://www.w3.org/2000/svg"
    :width="width"
    :height="height"
    :viewBox="`0 0 ${width} ${height}`"
    class="icon"
  >
    <slot />
  </svg>
</template>

<script>
export default {
  name: 'SvgBase',
  props: {
    width: {
      type: Number,
      default: 0,
    },
    height: {
      type: Number,
      default: 0,
    },
  }
};
</script>

<style scoped>
.icon {
  fill: currentColor;
}
</style>
