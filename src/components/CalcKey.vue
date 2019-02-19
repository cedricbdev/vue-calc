<template>
  <div @click="emitKey" v-html="keyData.value"></div>
</template>

<script>
export default {
  name: "CalcKey",
  props: ["keyData"],
  data() {
    return {};
  },
  methods: {
    emitKey() {
      console.log(
        `"CalcKey" child component is emitting "Clicked" event with the key value: ${
          this.keyData
        }`
      );
      this.$emit("clicked", this.keyData);
    }
  }
};
</script>
