<template>
  <div class="lib-dev">
    start: <input type="range" v-model="startDegreesString" min="0" max="360" step="5">
    end: <input type="range" v-model="endDegreesString" min="0" max="360" step="5">
    <svg-base
      :width="40"
      :height="40"
      class="svg"
    >
      <svg-arc
        class="arc"
        :cx="20"
        :cy="20"
        :r="19"
        :start-degrees="startDegrees"
        :end-degrees="endDegrees"
      />
    </svg-base>
  </div>
</template>

<script>
import { SvgBase, SvgArc } from "./entry";
export default {
  name: "VueSvgPrimitivesLibDev", // vue library dev component
  components: {
    SvgBase,
    SvgArc,
  },
  data() {
    return {
      startDegreesString: '45',
      endDegreesString: '0',
    }
  },
  computed: {
    startDegrees() {
      return parseInt(this.startDegreesString, 10);
    },
    endDegrees() {
      return parseInt(this.endDegreesString, 10);
    },
  }
};
</script>

<style scoped>
.lib-dev {
  display: block;
  width: 400px;
  margin: 25px auto;
}

.svg {
  width: 200px;
  height: 200px;
}

.arc {
  fill: transparent;
  stroke: blueviolet;
  stroke-width: 2;
}
</style>
