<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
  import {mapState, mapGetters} from 'vuex';

  export default {
    name: 'app',
    computed: {
      ...mapGetters(['isLogin', 'loginStatus'])
    },
    watch: {
      // 监听路由变化
      '$route': {
        handler() {
          let _this = this;

          _this.$store.dispatch('renderMarkdown', '');
        }
      },

      // 监听登录状态
      'loginStatus': {
        handler(value) {
          // 如果登录状态为false，就跳转到登录页面
          if (!value.status) {
            this.$router.push({
              path: '/login'
            });
          };
        }
      }
    }
  }
</script>

<style lang="less">
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Helvetica Neue", Helvetica, "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", "微软雅黑", Arial, sans-serif;
  }

  body {
    color: #505050;
    background-color: #EBEDF2;
  }

  .clear-float {
    zoom: 1;

    &:after {
      content: "";
      display: block;
      clear: both;
      visibility: hidden;
      height: 0;
    }
  }
</style>
