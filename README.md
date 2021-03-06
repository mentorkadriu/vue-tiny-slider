# vue-tiny-slider


## Table of Contents

* [Installation](#installation)
* [Usage](#usage)
* [Demo](#demo)
* [Development](#development)

## Installation
```
npm install @mentorkadriu/vue-tiny-slider
```
## Usage

More usage options can be found in the:
- [Full demos](https://vue-tiny-slider.vercel.app/)
- [/src/demos](https://github.com/mentorkadriu/vue-tiny-slider/tree/main/src/demos).
- [stackblitz.com](https://stackblitz.com/edit/vue-z2kxue)

```vue
<script>
  import { ref, onMounted } from "vue";
  import VueTinySlider from "@mentorkadriu/vue-tiny-slider";

  export default {
  name: "App",
  components: { VueTinySlider },
  setup() {
    // Optional: Create a ref to hold the slider value
    const slider = ref(null);
    
    // https://github.com/ganlanyuan/tiny-slider#options
    const options = {
      items: 3,
      speed: 400
    }
    onMounted(() => {
      // Get slider instance
      console.log(slider.value.getSlider());
    });


    function onIndexChange(info) {
      console.log(info);
    }
    
    return {
      onIndexChange,
      options,
      slider,
    };
  },
};
</script>

<template>
  <VueTinySlider :options="options" ref="slider" @indexChanged="onIndexChange">
    <div>Slide #1</div>
    <div>Slide #2</div>
    <div>Slide #3</div>
  </VueTinySlider>
</template>
```
## Development

### Setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build-lib
```
