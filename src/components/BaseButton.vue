<template>
  <button :style="cssPros">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "BaseButton",
  props: {
    color: {
      type: String,
      default: "primary",
    },
  },
  data() {
    return {
      inactive: true,
      colorPalette: {
        primary: {
          "--bg": "#42b983",
          "--hoverBg": "#4cce93",
          "--focusBorder": "#47d696",
        },
        warn: {
          "--bg": "#ff5722",
          "--hoverBg": "#ff7043",
          "--focusBorder": "#ff8a65",
        },
        danger: {
          "--bg": "#e53935",
          "--hoverBg": "#ef5350",
          "--focusBorder": "#e57373",
        },
      },
    };
  },
  computed: {
    cssPros() {
      return this.colorPalette[this.color];
    },
  },
};
</script>

<style scoped>
button {
  width: 200px;
  height: 30px;

  border-radius: 25px;
  background-color: var(--bg);
  border: 0px;
  margin: 5px;
}

button:disabled {
  opacity: 0.33;
}

button:not(:disabled):hover {
  background-color: var(--hoverBg);
}

button:focus {
  outline: none;
  box-shadow: 0 0 0 0.125em var(--focusBorder);
}
</style>
