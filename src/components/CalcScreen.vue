<template>
  <div id="calc-screen">{{ renderScreen }}</div>
</template>

<script>
export default {
  props: ["value"],
  computed: {
    renderScreen() {
      // stuff to do before rendering screen (filtering operations keys, reseting display if needed etc.)
      return this.value;
    }
  }
};
</script>

<style scoped>
#calc-screen {
  font-weight: bold;
  height: 50px;
  width: 100%;
  border-radius: 4px;
  position: absolute;
  top: 0;
  left: 0;
  text-align: right;
  line-height: 50px;
  overflow: hidden;
  padding: 0 10px;
}
</style>
