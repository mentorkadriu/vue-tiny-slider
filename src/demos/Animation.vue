<script>
import { ref } from "vue";
import VueTinySlider from "@/components/VueTinySlider";
import Slides from "@/demos/slides/Slides";

export default {
  name: "Animation",
  components: { Slides, VueTinySlider },
  setup() {
    let slider = ref(null);
    const sliderOptions = {
      mode: "gallery",
      items: 2,
      animateIn: "jello",
      animateOut: "rollOut",
      speed: 1000,
      swipeAngle: false,
    };

    return {
      sliderOptions,
      slider,
    };
  },
};
</script>

<template>
  <h2>Animation</h2>
  <VueTinySlider :options="sliderOptions" ref="slider">
    <Slides />
  </VueTinySlider>
  <div class="slider-options">
    <pre>
      {{ sliderOptions }}
    </pre>
  </div>
</template>
