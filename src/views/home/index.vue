<template>
  <el-container class="wrapper">
    <el-aside :width="isCollapse?'64px':'200px'">
      <div class="logo" :class="{miniLogo:isCollapse}"></div>
      <el-menu
        default-active="1"
        background-color="#002033"
        text-color="#fff"
        active-text-color="#ffd04b"
        :collapse="isCollapse"
        :collapse-transition="false"
      >
        <el-menu-item index="1">
          <i class="el-icon-s-home"></i>
          <span slot="title">首页</span>
        </el-menu-item>
        <el-menu-item index="2">
          <i class="el-icon-document"></i>
          <span slot="title">内容管理</span>
        </el-menu-item>
        <el-menu-item index="3">
          <i class="el-icon-picture"></i>
          <span slot="title">素材管理</span>
        </el-menu-item>
        <el-menu-item index="4">
          <i class="el-icon-s-promotion"></i>
          <span slot="title">发布文章</span>
        </el-menu-item>
        <el-menu-item index="5">
          <i class="el-icon-chat-dot-round"></i>
          <span slot="title">评论管理</span>
        </el-menu-item>
        <el-menu-item index="6">
          <i class="el-icon-present"></i>
          <span slot="title">粉丝管理</span>
        </el-menu-item>
        <el-menu-item index="7">
          <i class="el-icon-setting"></i>
          <span slot="title">个人设置</span>
        </el-menu-item>
      </el-menu>
    </el-aside>
    <el-container>
      <el-header>
        <span class="el-icon-s-fold" @click="toggleMenu"></span>
        <span class="text">江苏传智播客科技教育有限公司</span>
        <el-dropdown class="my-dropdown">
          <span class="el-dropdown-link">
            <img src="../../assets/images/avatar.jpg" alt />
            你瞅啥
            <i class="el-icon-arrow-down el-icon--right"></i>
          </span>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item>个人设置</el-dropdown-item>
            <el-dropdown-item>退出登录</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
      </el-header>
      <el-main>
        <router-view></router-view>
      </el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {
  data () {
    return {
      isCollapse: false
    }
  },
  methods: {
    toggleMenu () {
      this.isCollapse = !this.isCollapse
    }
  }
}
</script>

<style scoped lang="less">
.wrapper {
  width: 100%;
  height: 100%;
  position: absolute;
  left: 0;
  top: 0;
  .el-aside {
    background-color: #002033;
  }
  .logo {
    width: 100%;
    height: 60px;
    background: #002244 url(../../assets/images/logo_admin.png) no-repeat center /
      140px auto;
  }
  .miniLogo {
    background-image: url(../../assets/images/logo_admin_01.png);
    background-size: 36px auto;
  }
  .el-menu {
    border-right: none;
  }

  .el-header {
    border-bottom: 1px solid #ccc;
    line-height: 64px;
    .el-icon-s-fold {
      font-size: 28px;
      vertical-align: middle;
    }
    .text {
      font-size: 16px;
      vertical-align: middle;
    }
    .my-dropdown {
      float: right;
      img {
        width: 30px;
        height: 30px;
        vertical-align: middle;
      }
      .el-dropdown-link {
        font-weight: bold;
      }
    }
  }
}
</style>
