<template>
  <div>
    <div
      class="skeleton-card"
      :style="{
      background: primary,
      borderRadius,
      padding
  }"
    >
      <div
        class="skeleton-card-loader"
        :style="{
      background: loaderBackground,
      animationDuration: animDuration,
      animationTimingFunction: animTimingFunction
    }"
        v-if="!animDisable"
      ></div>
      <slot />
    </div>
  </div>
</template>

<script>
import tinycolor from "tinycolor2";

export default {
  name: "SkeletonScaffold",
  props: {
    primary: {
      type: String,
      default: "#242424",
    },
    padding: {
      type: String,
      default: "2em 3em",
    },
    borderRadius: {
      type: String,
      default: "0",
    },
    animDuration: {
      type: String,
      default: "1.5s",
    },
    animDisable: {
      type: Boolean,
      default: false,
    },
    animTimingFunction: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      loaderBackground: tinycolor(this.primary).lighten(6).toString(),
    };
  },
};
</script>

<style>
</style>