<template>
  <div class="card-layout">
    <div class="circle-icon">
      <img src="@/assets/svg/ic_plan.svg" alt=""></img>
    </div>
    <span class="text">{{ text }}</span>
    <span class="count">{{ count }}</span>


  </div>
</template>

<script>
// 只有通过 export default 导出的组件，才能被其他文件通过 import 引入使用
export default {
  name: 'CardItem',
  // 数据定义部分
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
  // width: 80%;
  // margin-top: 8px;
  background: #cbcbcb;
  position: relative;

  .circle-icon {
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 50%;
    width: 24px;
    height: 24px;
    background-color: red;
  }
  img{
    width: 16px;
    height: 16px;
  }
  .count{
    font-weight: bold;
    color: black;
    font-size: 16px;
    right: 8px;
    position: absolute;
    top: 8px;
  }
  .text{
    font-size: 14px;
    color: #4c4c4c;
    font-weight: normal;
  }
}

</style>