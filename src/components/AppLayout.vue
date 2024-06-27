<!-- 
 AppLayout
 页面的整体布局，包括Header、Content、Footer
 其中 Content 用 AppContent 组件表示
-->

<script setup>
import {ref} from 'vue';

const selectedKeys = ref(['1']);
</script>

<template>
  <a-layout class="layout">
    <!--Header-->
    <a-layout-header>
      <div class="logo"/>
      <a-menu
          class="menu"
          v-model:selectedKeys="selectedKeys"
          theme="dark"
          mode="horizontal"
          :style="{ lineHeight: '64px' }"
      >
        <a-menu-item class="menu-item" key="1">表相关</a-menu-item>
        <a-menu-item class="menu-item" key="2">字段相关</a-menu-item>
        <a-menu-item class="menu-item" key="3">数据相关</a-menu-item>
      </a-menu>
    </a-layout-header>
    <!--Content-->
    <a-layout-content class="content-container">
      <!--面包屑-->
      <a-breadcrumb class="content-breadcrumb">
        <a-breadcrumb-item>Home</a-breadcrumb-item>
        <a-breadcrumb-item>List</a-breadcrumb-item>
        <a-breadcrumb-item>App</a-breadcrumb-item>
      </a-breadcrumb>
      <!--应用内容-->
      <div class="content-main">
        <!-- 替换成AppContent组件 -->
        <slot></slot>
      </div>
    </a-layout-content>
    <!--Footer-->
    <a-layout-footer>
      Ant Design ©2018 Created by Ant UED
    </a-layout-footer>
  </a-layout>
</template>

<style scoped>

.layout {
  height: 100vh;
}
.content-container {
  display: flex;
  flex-direction: column;
  padding: 0 50px;
}

.content-breadcrumb {
  flex-grow: 0;
  margin: 16px 0;
  text-align: center;
}

.content-main {
  flex-grow: 1;
  background: #fff;
  padding: 24px;
}

a-layout-footer {
  text-align: center;
}

.menu :deep(.menu-item) {
  font-weight: bold;
}
</style>