<template>
  <div id="app">
    <feature-list></feature-list>
  </div>
</template>

<script>
import FeatureList from './components/FeatureList';

export default {
  name: 'app',
  components: {
    FeatureList,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
