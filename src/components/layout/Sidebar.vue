<template>
  <div class="sidebar">
    <el-menu default-active="1-1"
             :router="true"
             @open="handleOpen"
             @close="handleClose">
      <el-submenu index="1">
        <template slot="title"><i class="el-icon-edit"></i>文章操作</template>
        <el-menu-item index="1-1"
                      :route="{path:'/'}">
          文章列表
        </el-menu-item>
        <el-menu-item index="1-2"
                      :route="{path:'/create'}">
          新建文章
        </el-menu-item>
      </el-submenu>
      <el-menu-item index="2"><i class="el-icon-menu"></i>分类</el-menu-item>
      <el-menu-item index="3"><i class="el-icon-setting"></i>导航三</el-menu-item>
    </el-menu>
  </div>
</template>

<script>
  export default {
    name: 'sidebar',
    data() {
      return {}
    },
    methods: {
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>

<style scoped lang="less">
  .sidebar {

  }
</style>

