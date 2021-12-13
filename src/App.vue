<script>
import "./assets/css/demo.css";
import "tiny-slider/src/tiny-slider.scss";
import BaseDemo from "@/demos/BaseDemo";
import Base from "@/demos/Base";
import AutoWidth from "@/demos/AutoWidth";
import AutoWidthNonLoop from "@/demos/AutoWidthNonLoop";
import AutoWidthLazyLoad from "@/demos/AutoWidthLazyLoad";
import Animation from "@/demos/Animation";
import Customize from "@/demos/Customize";

export default {
  name: "App",
  components: {
    Customize,
    Animation,
    AutoWidthLazyLoad,
    AutoWidthNonLoop,
    AutoWidth,
    Base,
    BaseDemo,
  },
};
</script>

<template>
  <Base />
  <BaseDemo
    title="Start index"
    :options="{
      items: 3,
      slideBy: 'page',
      loop: false,
      startIndex: 6,
      swipeAngle: false,
      speed: 400,
    }"
  />
  <BaseDemo
    title="Non-loop"
    :options="{
      loop: false,
      responsive: {
        '350': {
          items: 2,
        },
        '500': {
          items: 3,
        },
      },
      swipeAngle: false,
      speed: 400,
    }"
  />
  <BaseDemo
    title="Rewind"
    :options="{
      items: 3,
      rewind: true,
      swipeAngle: false,
      speed: 400,
    }"
  />
  <BaseDemo
    title="Center"
    :options="{
      items: 2,
      center: true,
      loop: false,
      swipeAngle: false,
      speed: 400,
    }"
  />
  <BaseDemo
    title="Fixedwidth"
    :options="{
      items: 3,
      fixedWidth: 400,
      swipeAngle: false,
      speed: 400,
    }"
  />
  <BaseDemo
    :options="{
      items: 3,
      edgePadding: 50,
      fixedWidth: 400,
      swipeAngle: false,
      speed: 400,
    }"
    title="Fixedwidth-edgepadding"
  />
  <AutoWidth />
  <AutoWidthNonLoop />
  <AutoWidthLazyLoad />
  <BaseDemo
    :options="{
      items: 3,
      axis: 'vertical',
      swipeAngle: false,
      speed: 400,
    }"
    title="Vertical"
  />
  <BaseDemo
    :options="{
      items: 2,
      controls: false,
      responsive: {
        '350': {
          items: 3,
          controls: true,
          edgePadding: 30,
        },
        '500': {
          items: 4,
        },
      },
      swipeAngle: false,
      speed: 400,
    }"
    title="Responsive"
  />
  <BaseDemo
    :options="{
      items: 3,
      speed: 300,
      autoplay: true,
      autoplayHoverPause: true,
      autoplayTimeout: 3500,
      autoplayText: ['▶', '❚❚'],
      swipeAngle: false,
    }"
    title="Autoplay"
  />
  <Animation />
  <Customize />
</template>

<style lang="scss">
.slider-options {
  background-color: #f5f2f0;
  padding: 20px;
  display: flex;
  justify-content: center;
}
</style>
