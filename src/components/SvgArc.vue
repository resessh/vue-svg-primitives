<template>
  <circle
    v-if="isCircle"
    :cx="cx"
    :cy="cy"
    :r="r"
  />
  <path
    v-else
    :d="d"
  />
</template>

<script>
export default {
  props: {
    cx: {
      type: Number,
      default: 0,
    },
    cy: {
      type: Number,
      default: 0,
    },
    r: {
      type: Number,
      default: 0,
    },
    startDegrees: {
      type: Number,
      default: 0,
    },
    endDegrees: {
      type: Number,
      default: 180,
    },
  },
  computed: {
    diffOfDegrees() {
      return this.startDegrees - this.endDegrees;
    },
    startX() {
      return this.cx + this.r * Math.cos(this.startDegrees / 360 * 2 * Math.PI);
    },
    startY() {
      return this.cy - this.r * Math.sin(this.startDegrees / 360 * 2 * Math.PI);
    },
    endX() {
      return this.cx + this.r * Math.cos(this.endDegrees / 360 * 2 * Math.PI);
    },
    endY() {
      return this.cy - this.r * Math.sin(this.endDegrees / 360 * 2 * Math.PI);
    },
    largeArcFlag() {
      return Math.abs(this.diffOfDegrees) > 180 ? 1 : 0;
    },
    sweepFlag() {
      return this.diffOfDegrees > 0 ? 1 : 0;
    },
    isCircle() {
      return Math.abs(this.diffOfDegrees) === 360;
    },
    d() {
      return `M ${this.startX} ${this.startY} A ${this.r} ${this.r} 0 ${this.largeArcFlag} ${this.sweepFlag} ${this.endX} ${this.endY}`;
    }
  }
}
</script>
