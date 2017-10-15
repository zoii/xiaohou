<template>
  <aside class="feature-aside">
    <dl class="feature-menu">
      <dt>{{data.name}}</dt>
      <dd v-for="item in data.children" v-bind:key="item.id">{{item.name}}</dd>
    </dl>
  </aside>
</template>

<script>
export default {
  name: 'FeatureMenu',
  props: {
    data: [],
  },
  data() {
    return {
    };
  },
  methods: {
  },
};
</script>

<style scoped>
  .feature-menu dt {
    margin: 0;
    text-align: left;
    font-size: 16px;
  }
  .feature-menu dd {
    margin: 0 0 0 24px;
    padding: 0;
    text-align: left;
    font-size: 14px;
  }
</style>