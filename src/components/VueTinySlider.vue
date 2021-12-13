<script>
import { ref, onUnmounted, onMounted, h } from "vue";
import { tns } from "tiny-slider/src/tiny-slider";

export default {
  name: "VueTinySlider",
  props: {
    options: {
      type: Object,
      default() {
        return {
          items: 1,
        };
      },
    },
  },
  setup(props, { slots, expose }) {
    const root = ref(null);
    let slider;

    onMounted(() => {
      slider = tns({
        container: root.value,
        ...props.options,
      });
    });
    onUnmounted(() => {
      slider.destroy();
    });

    expose({
      getSlider() {
        return slider;
      },
    });

    return () => h("div", { ref: root }, slots);
  },
};
</script>
