<template>
  <div class="home">
    <el-container>
      <el-aside width='auto'>
        <sidebar />
      </el-aside>
      <el-container>
        <el-header>
          <navbar />
        </el-header>
        <tags-view/>
        <el-main>
          <appmain />
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
// @ is an alias to /src
import sidebar from '@/layout/sidebar/index.vue'
import navbar from '@/layout/navbar/index.vue'
import appmain from '@/layout/Appmain.vue'
import TagsView from '@/layout/TagsView/index.vue'

export default {
  name: 'home',
  components: {
    sidebar,
    navbar,
    appmain,
    TagsView
  }
}
</script>
<style lang="scss" scoped>
.el-main{
  padding: 0;
  background-color: #f0f2f5;
}
.el-header{
  height: 50px!important;
  padding: 0;
  box-shadow: 0 1px 4px rgba(0,21,41,0.08);
}
</style>

