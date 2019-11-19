<template>
  <div class="sidebar">
    <el-menu
      :default-active="activeMenu"
      class="el-menu-vertical-demo"
      :collapse="isCollapse"
      :router='true'
    >
      <el-menu-item index="/home" route="/">
        <svg-icon icon-class="home" />
        <span slot="title">Home</span>
      </el-menu-item>
      
      <el-menu-item index="/dashboard">
        <!-- <i class="el-icon-menu"></i> -->
        <svg-icon icon-class="dashboard" />
        <span slot="title">Dashboard</span>
      </el-menu-item>
      <el-menu-item index="/icons">
        <svg-icon icon-class="icon" />
        <span slot="title">Icons</span>
      </el-menu-item>
      <el-submenu index="/upload">
        <template slot="title">
          <i class="el-icon-upload2" />
          <span slot="title">Upload</span>
        </template>
        <el-menu-item index="/upload/avatar">Avatar</el-menu-item>
      </el-submenu>
    </el-menu>
  </div>
</template>
<script>
export default {
  data() {
    return {};
  },
  computed: {
    isCollapse() {
      return !this.$store.state.sidebar.opened;
    },
    activeMenu() {
      const route = this.$route
      const { meta, path } = route
      // if set path, the sidebar will highlight the path you set
      if (meta.activeMenu) {
        return meta.activeMenu
      }
      return path
    },
  },
  methods: {

  },
  mounted(){
      console.log(this.$route)
  }
};
</script>
<style lang="scss" scoped>
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  min-height: 400px;
}
.svg-icon{
  margin-right: 16px;
}
</style>