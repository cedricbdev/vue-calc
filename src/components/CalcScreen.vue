<template>
  <div id="calc-screen">{{ value }}</div>
</template>

<script>
export default {
  props: ["value"]
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
