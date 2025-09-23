<!-- <template>
  <div class="card-layout">
    <div class="circle-icon">
      <img src="src/assets/svg/ic_plan.svg" alt="" />
    </div>
    <span class="text">{{ text }}</span>
    <span class="count">{{ count }}</span>
  </div>
</template>
<script>
export default {
  name: 'CardItem',
  data() {
    return {
      type: 1,
      count: 2,
      text: '今天',
    }
  },
}
</script>
<style scoped lang="scss">
.card-layout {
  padding: 8px;
  border-radius: 12px;
  background-color: #cbcbcb;
  position: relative;

  .circle-icon {
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 50%;
    width: 24px;
    height: 24px;
    background-color: red;

    img {
      width: 16px;
      height: 16px;
    }
  }

  .text {
    font-size: 14px;
    color: #4c4c4c;
    font-weight: normal;
  }

  .count {
    font-size: 16px;
    color: black;
    font-weight: bold;
    position: absolute;
    right: 8px;
    top: 8px;
  }
}
</style> -->
<template>
  <div class="card-layout">
    <div class="circle-icon">
      <img :src="iconSrc" alt="" />
    </div>
    <span class="text">{{ text }}</span>
    <span class="count">{{ count }}</span>
  </div>
</template>

<script>
import icPlanSvg from '@/assets/svg/ic_plan.svg' // 使用 @ 别名

export default {
  name: 'CardItem',
  data() {
    return {
      type: 1,
      count: 2,
      text: '今天',
      iconSrc: icPlanSvg, // 绑定到 img 的 src
    }
  },
}
</script>
