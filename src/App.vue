<template>
  <div id="app">
    <div class="linha">
      <conVs moeda-a="USD" moeda-b="BRL"/>
      <conVs moeda-a="BRL" moeda-b="USD"/>
    </div>
    <div class="linha">
      <conVs moeda-a="CAD" moeda-b="BRL"/>
      <conVs moeda-a="BRL" moeda-b="CAD"/>
    </div>
    <div class="linha">
      <conVs moeda-a="EUR" moeda-b="BRL"/>
      <conVs moeda-a="BRL" moeda-b="EUR"/>
    </div>
  </div>
</template>

<script>
import conVs from "./components/cvt.vue";
export default {
  name: "app",
  components: {
    conVs,
  }
};

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  display: flex;
  justify-content: center;
  background-color: #ffffff;
}
</style>
