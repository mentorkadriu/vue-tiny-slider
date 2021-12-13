<script>
import { ref } from "vue";
import VueTinySlider from "@/components/VueTinySlider";

export default {
  name: "AutoWidthNonLoop",
  components: { VueTinySlider },
  setup() {
    let slider = ref(null);
    const sliderOptions = {
      autoWidth: true,
      loop: false,
      mouseDrag: true,
      swipeAngle: false,
      speed: 400,
    };

    return {
      sliderOptions,
      slider,
    };
  },
};
</script>

<template>
  <h2>Autowidth-non-loop</h2>
  <VueTinySlider :options="sliderOptions" ref="slider" class="autowidth">
    <div class="item">
      <img
        src="https://source.unsplash.com/collection/993239/600x320"
        width="600"
        height="320"
        alt=""
      />
    </div>
    <div class="item">
      <img
        src="https://source.unsplash.com/collection/1673600/500x300"
        width="500"
        height="300"
        alt=""
      />
    </div>
    <div class="item">
      <img
        src="https://source.unsplash.com/collection/1513994/200x310"
        width="200"
        height="310"
        alt=""
      />
    </div>
    <div class="item">
      <img
        src="https://source.unsplash.com/collection/502925/400x330"
        width="400"
        height="330"
        alt=""
      />
    </div>
    <div class="item">
      <img
        src="https://source.unsplash.com/collection/1891993/640x300"
        width="640"
        height="300"
        alt=""
      />
    </div>
    <div class="item">
      <img
        src="https://source.unsplash.com/collection/1103088/360x240"
        width="360"
        height="240"
        alt=""
      />
    </div>
    <div class="item">
      <img
        src="https://source.unsplash.com/collection/548245/460x280"
        width="460"
        height="280"
        alt=""
      />
    </div>
  </VueTinySlider>
  <div class="slider-options">
    <pre>{{ sliderOptions }}</pre>
  </div>
</template>
