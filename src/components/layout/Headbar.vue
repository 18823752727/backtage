<template>
  <header class="header">
    <div class="user-info">
        <span class="user-name">
          {{userName}}
        </span>
      <span class="layout" @click="layout">
          退出
        </span>
    </div>
  </header>
</template>

<script>
  import api from "../../http";
  import {mapGetters,mapActions} from 'vuex';

  export default {
    name: 'headbar',
    data() {
      return {}
    },
    computed: {
      ...mapGetters(['userName'])
    },
    methods: {
      ...mapActions(['clearUserInfo']),
      layout() {
        let _this = this;

        api.layout().then(() => {
          // 清除用户信息
          _this.clearUserInfo();

          // 跳转到登录界面
          _this.$router.push({
            path: '/login'
          });


        })
      }
    }
  }
</script>

<style lang="less" scoped>
  header {
    width: 100%;
    height: 60px;
    padding: 0 30px;
    background-color: black;

    .user-info {
      float: right;
      height: 60px;
      line-height: 60px;
      color: #fff;

      .layout {
        margin-left: 20px;
        cursor: pointer;
      }
    }
  }
</style>
