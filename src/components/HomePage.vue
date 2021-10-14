<template>
  <div>
    <AsyncButton @click="waitFor2Second">
      HomePage disable for 2 second</AsyncButton
    >
  </div>
</template>

<script>
import AsyncButton from "./AsyncButton.vue";

export default {
  components: {
    AsyncButton,
  },
  name: "HomePage",
  data() {
    return {
      waiting: 2000,
    };
  },
  methods: {
    waitFor2Second() {
      return new Promise((resolve) =>
        setTimeout(() => resolve(), this.waiting)
      );
    },
  },
};
</script>

<style scoped></style>
