<!-- <template>
  <div class="main-container">
    <menu-layout class="menu-container"></menu-layout>
    <div class="content-container">111</div>
  </div>
</template>

<script>
import MenuLayout from '@/components/menu/MenuLayout.vue'

export default {
  name: 'MainView', // 组件名称（用于调试和递归引用
  components: {
    // 注册子组件
    MenuLayout, // 使 <menu-layout> 可在模板中使用
  },
}
</script>

<style scoped></style> -->
<template>
  <div class="main-container">
    <menu-layout class="menu-container" />
    <div class="content-container">22</div>
  </div>
</template>
<script>
import MenuLayout from '@/components/menu/MenuLayout.vue'

export default {
  name: 'MainView',
  components: {
    MenuLayout,
  },
}
</script>
<style scoped></style>
