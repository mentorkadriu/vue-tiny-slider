<script>
import { ref } from "vue";
import VueTinySlider from "@/components/VueTinySlider";
import Slides from "@/demos/slides/Slides";

export default {
  name: "Base",
  components: { Slides, VueTinySlider },
  setup() {
    let slider = ref(null);
    const sliderOptions = {
      items: 3,
      slideBy: "page",
      mouseDrag: true,
      swipeAngle: false,
      speed: 400,
    };
    const toSlide = ref(3);

    function goToSlide() {
      slider.value.getSlider().goTo(toSlide.value);
    }

    function onIndexChange(info) {
      console.log(info);
    }

    return {
      onIndexChange,
      sliderOptions,
      slider,
      goToSlide,
      toSlide,
    };
  },
};
</script>

<template>
  <h2>Base</h2>
  <div class="goto-controls">
    Go to slide: <input type="text" v-model="toSlide" />
    <button class="button" @click="goToSlide">Go</button>
  </div>
  <VueTinySlider :options="sliderOptions" ref="slider" @indexChanged="onIndexChange">
    <Slides />
  </VueTinySlider>
  <div class="slider-options">
    <pre>{{ sliderOptions }}</pre>
  </div>
</template>
