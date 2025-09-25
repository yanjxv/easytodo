<template>
  <div class="main-container">
    <!-- 可以使用已注册的子组件 -->
    <menu-layout class="menu-container"></menu-layout>
    <div class="content-container">111</div>
  </div>
</template>
<script>
import MenuLayout from '@/components/menu/MenuLayout.vue'
export default {
  name: 'MainView', // 组件名称
  components: {
    MenuLayout, // 注册子组件
  },
}
</script>
<style scoped></style>
