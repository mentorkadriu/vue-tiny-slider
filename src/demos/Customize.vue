<script>
import { ref } from "vue";
import VueTinySlider from "@/components/VueTinySlider";
import UnsplashSlides from "@/demos/slides/UnsplashSlides";
import angleLeft from "@/assets/images/angle-left.png";
import angleRight from "@/assets/images/angle-right.png";

export default {
  name: "Customize",
  components: { UnsplashSlides, VueTinySlider },
  setup() {
    let slider = ref(null);
    const sliderOptions = {
      items: 3,
      controlsContainer: "#customize-controls",
      navContainer: "#customize-thumbnails",
      navAsThumbnails: true,
      autoplay: true,
      autoplayTimeout: 4000,
      autoplayButton: "#customize-toggle",
      swipeAngle: false,
      speed: 400,
    };

    return {
      sliderOptions,
      slider,
      angleRight,
      angleLeft
    };
  },
};
</script>

<template>
  <h2>Customize</h2>
  <VueTinySlider :options="sliderOptions" ref="slider">
    <UnsplashSlides />
  </VueTinySlider>
  <div class="customize-tools">
    <ul class="thumbnails" id="customize-thumbnails">
      <li>
        <img src="https://source.unsplash.com/collection/993239/600x400" alt="" width="600" height="400">
      </li>
      <li>
        <img src="https://source.unsplash.com/collection/1673600/600x400" alt="" width="600" height="400">
      </li>
      <li>
        <img src="https://source.unsplash.com/collection/1513994/600x400" alt="" width="600" height="400">
      </li>
      <li>
        <img src="https://source.unsplash.com/collection/502925/600x400" alt="" width="600" height="400">
      </li>
      <li>
        <img src="https://source.unsplash.com/collection/1891993/600x400" alt="" width="600" height="400">
      </li>
    </ul>
    <ul class="controls" id="customize-controls">
      <li class="prev">
        <img :src="angleLeft" alt="left">
      </li>
      <li class="next">
        <img :src="angleRight" alt="right">
      </li>
    </ul>
    <div class="playbutton-wrapper">
      <button id="customize-toggle">Pause</button>
    </div>
  </div>
  <div class="slider-options">
    <pre>
      {{ sliderOptions }}
    </pre>
  </div>
</template>
