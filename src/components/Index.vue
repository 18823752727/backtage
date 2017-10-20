<template>
  <div class="mangoxin">
    <!--头部-->
    <headbar></headbar>

    <!--内容区域-->
    <div class="section">
      <!--左边侧边栏导航-->
      <sidebar></sidebar>

      <!--右边内容区-->
      <div class="mangoxin-content">
        <router-view></router-view>
      </div>
    </div>

  </div>
</template>

<script>
  import api from "../http";
  import Headbar from "./layout/Headbar.vue";
  import Sidebar from './layout/Sidebar.vue';

  export default {
    name: 'index',
    data() {
      return {}
    },
    components: {
      Headbar,
      Sidebar,
    },

    methods: {}
  }
</script>


<style lang="less">
  .mangoxin {
    min-width: 1200px;

    .header {

    }

    .section {
      display: flex;
      flex-wrap: nowrap;

      .sidebar {
        width: 200px;
        height: 100px;
        background-color: coral;
      }

      .mangoxin-content {
        width: 100%;
        padding: 20px;
        min-height: 500px;
        background-color: #fff;
      }
    }
  }
</style>

