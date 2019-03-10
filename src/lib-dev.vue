<script>
import { SvgBase } from "./entry";
export default {
  name: "VueSvgPrimitivesLibDev", // vue library dev component
  components: {
    SvgBase
  }
};
</script>

<template>
  <div class="lib-dev">
    <svg-base>hoge</svg-base>
  </div>
</template>

<style scoped>
.lib-dev {
  display: block;
  width: 400px;
  margin: 25px auto;
}
</style>
