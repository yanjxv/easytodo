<template>
  <div>
    <input type="text" name="" id="" placeholder="搜索" />
    <card-item style="width: 200px" />
  </div>
</template>
<script>
import CardItem from '@/components/menu/CardItem.vue'

export default {
  name: 'MenuLayout',
  components: {
    CardItem,
  },
}
</script>
<style scoped>
input {
  width: 100%;
  height: 30px;
  /* 设置为块级元素确保输入框下方的 CardItem 组件会换行显示在下一行 */
  display: block;
}
</style>
