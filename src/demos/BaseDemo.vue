<script>
import { ref } from "vue";
import VueTinySlider from "@/components/VueTinySlider";
import Slides from "@/demos/slides/Slides";

export default {
  name: "BaseDemo",
  props: {
    title: {
      type: String,
      required: true,
    },
    options: {
      type: Object,
      default() {
        return {
          items: 3,
        };
      },
    },
  },
  components: { Slides, VueTinySlider },
  setup() {
    let slider = ref(null);

    return {
      slider,
    };
  },
};
</script>

<template>
  <h2>{{ title }}</h2>
  <VueTinySlider :options="options" ref="slider">
    <Slides />
  </VueTinySlider>
  <div class="slider-options">
    <pre>{{ options }}</pre>
  </div>
</template>
