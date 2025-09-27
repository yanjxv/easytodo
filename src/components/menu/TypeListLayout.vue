<template>
  <div class="type-list-layout">
    <h3>我的列表</h3>
    <transition-group name="list">
      <type-item
        v-for="item in list"
        :name="item.name"
        :key="item.id"
        :count="item.count"
        class="menu-item-layout"
      />
    </transition-group>
  </div>
</template>
<script>
import TypeItem from '@/components/menu/TypeItem.vue'
export default {
  name: 'TypeListLayout',
  components: {
    TypeItem,
  },
  data() {
    return {
      list: [
        { color: 1, name: 'name1', count: 2, id: 1 },
        { color: 2, name: 'name2', count: 0, id: 2 },
        { color: 4, name: 'name3', count: 2, id: 3 },
        { color: 1, name: 'name4', count: 5, id: 4 },
      ],
    }
  },
}
</script>
<style scoped lang="scss">
.type-list-layout {
  padding: 16px 0;
  display: flex;
  flex-direction: column;
  h3 {
    padding-left: 12px;
    font-size: 12px;
    color: var(--todo-text-gray2);
  }
  .menu-item-layout {
    height: 36px;
    width: 100%;
  }
}
</style>
