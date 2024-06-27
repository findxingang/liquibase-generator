<script setup>
import AppLayout from "@/components/AppLayout.vue"
import AppContent from './components/AppContent.vue';

</script>

<template>
  <!-- 应用整体页面布局 -->
  <AppLayout>
    <!-- 应用内容，是一个可变区域，通过slot插入页面整体布局中 -->
    <!-- 直接在AppContent组件中设置网页内容 -->
    <AppContent></AppContent>
  </AppLayout>
</template>

<style scoped>

</style>