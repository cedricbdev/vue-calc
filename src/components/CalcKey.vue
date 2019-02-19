<template>
  <div @click="emitKey" v-html="value"></div>
</template>

<script>
export default {
  name: "CalcKey",
  props: ["value"],
  data() {
    return {};
  },
  methods: {
    emitKey() {
      console.log(
        `"CalcKey" child component is emitting "Clicked" event with the key value: ${
          this.value
        }`
      );
      this.$emit("clicked", this.value);
    }
  }
};
</script>
