<template>
  <div class="feature-item">
    <div class="feature-title">
      <h3>{{data.name}}</h3>
    </div>
    <div class="feature-content" v-for="item in data.children" v-bind:key="item.id" >
      <h4>
        <img :src="item.pic" class="icon-36" :alt="item.name">
        <b>{{item.name}}</b>
      </h4>
      <ul class="feature-attr">
        <li v-for="feature in item.children" v-bind:key="feature.id">
          <a href="#">
            <label>{{feature.name}}</label>
            <span class="feature-txt">
              <i class="icon-good" v-if="feature.score_txt === '好'"></i>
              <i class="icon-ordinary" v-if="feature.score_txt === '一般'"></i>
              <i class="icon-bad" v-if="feature.score_txt === '差'"></i>
              <span class="tez" v-for="(text, index) in feature.texts" v-bind:key="text.id">
                {{text}}
                <!-- <i v-if="feature.texts.length > 1">;</i> -->
              </span>
            </span>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FeatureItem',
  props: {
    data: {},
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
  .icon-36 {
    width: 36px;
    height: 36px;
  }
  .icon-16 {
    width: 16px;
    height: 16px;
  }
  .icon-good, .icon-ordinary, .icon-bad {
    display: inline-block;
    vertical-align: middle;
    margin-right: 10px;
    width: 24px;
    height: 24px;
    background: url(../assets/icon-master.png) no-repeat 0 0;
  }
  .icon-ordinary {
    background-position: 0 -24px;
  }
  .icon-bad {
    background-position: 0 -48px;
  }
  .feature-item {
    color: #333;
  }
  .feature-title {
    text-align: left;
    font-size: 24px;
    border-bottom: 1px solid #e8e8e8;
  }
  .feature-title h3 {
    position: relative;
    margin: 0;
    padding: 15px 0 15px 20px;
  }
  .feature-title h3::before {
    position: absolute;
    display: block;
    content: '';
    width: 4px;
    height: 24px;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    background: #fe6b01;
  }
  .feature-content {
    display: flex;
    padding: 50px;
    text-align: left;
    align-items: start;
  }
  .feature-content h4 {
    margin: 0;
    flex: 1;
    line-height: 1;
    font-size: 18px;
    font-weight: 500;
    text-align: center;
    
  }
  .feature-content h4 b{
    display: block;
    margin-top: 20px;
  }
  .feature-attr {
    flex: 9;
    padding: 0;
    margin: 0 0 0 55px;
  }
  .feature-attr li {
    list-style: none;
    text-align: left;
    border-bottom: 1px solid #e8e8e8;
    color: #333;
  }
  .feature-attr li:first-child a {
    padding-top: 0;
  }
  .feature-attr a {
    display: flex;
    position: relative;
    width: 100%;
    padding: 15px 0 15px 0;
    font-size: 14px;
    color: #666;
    text-decoration: none;
  }
  .feature-attr a:before {
    content: '';
    height: 8px;
    width: 8px;
    display: block;
    border: 1px solid #a8a8a8;
    border-left-width: 0;
    border-top-width: 0;
    transform: rotate(-45deg) translateY(-50%);
    position: absolute;
    top: 50%;
    right: 0;
  }
  .feature-attr label {
    width: 120px;
    font-weight: 900;
    color: #333;
  }
  .feature-txt {
    display: inline-block;
    padding-right: 30px;
  }
</style>