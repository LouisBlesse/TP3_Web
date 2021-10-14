<template>
  <BaseButton
    :disabled="isPending"
    :color="color"
    @click.stop.prevent="handleClick"
  >
    <slot />
  </BaseButton>
</template>

<script>
import BaseButton from "./BaseButton.vue";

export default {
  name: "AsyncButton",
  components: { BaseButton },
  inheritAttrs: false,
  props: {
    color: {
      type: String,
      default: "primary",
    },
  },
  data() {
    return {
      isPending: false,
    };
  },
  methods: {
    handleClick() {
      const originalOnClick = this.$attrs.onClick;
      this.isPending = true;
      originalOnClick().finally(() => {
        this.isPending = false;
      });
    },
  },
};
</script>
