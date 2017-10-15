<template>
  <div class="feature-group">
    <div class="feature-list">
      <feature-item :data="item" v-for="item in data" v-bind:key="item.id"></feature-item>
    </div>
    <aside class="feature-aside">
      <feature-menu :data="item" v-for="item in data" v-bind:key="item.id"></feature-menu>
    </aside>
  </div>
</template>


<script>
import Vue from 'vue';
import FeatureItem from './FeatureItem';
import FeatureMenu from './FeatureMenu';

export default {
  name: 'FeatureList',
  mounted() {
    this.fetchProduct();
    this.fetchOperations();
    this.fetchHardware();
    this.fetchService();
  },
  data() {
    return {
      data: [0, 1, 2, 3],
    };
  },
  methods: {
    fetchProduct() {
      const uri = 'https://www.wangdahu.net/api/index.php?g=home&m=PaperRecord&a=first_node_detail&node_id=136&company_id=91';
      Vue.http.get(uri)
      .then((res) => {
        this.data.splice(0, 0, res.body.data);
      });
    },
    fetchOperations() {
      const uri = 'https://www.wangdahu.net/api/index.php?g=home&m=PaperRecord&a=first_node_detail&node_id=137&company_id=91';
      Vue.http.get(uri)
      .then((res) => {
        this.data.splice(1, 0, res.body.data);
      });
    },
    fetchHardware() {
      const uri = 'https://www.wangdahu.net/api/index.php?g=home&m=PaperRecord&a=first_node_detail&node_id=138&company_id=91';
      Vue.http.get(uri)
      .then((res) => {
        this.data.splice(2, 0, res.body.data);
      });
    },
    fetchService() {
      const uri = 'https://www.wangdahu.net/api/index.php?g=home&m=PaperRecord&a=first_node_detail&node_id=139&company_id=91';
      Vue.http.get(uri)
      .then((res) => {
        this.data.splice(3, 0, res.body.data);
      });
    },
  },
  components: {
    FeatureItem,
    FeatureMenu,
  },
};
</script>

<style scoped>
 
</style>