<template>
  <div class="card-layout" :class="classObj">
    <div class="circle-icon">
      <img :src="imgsrc" alt=""></img>
    </div>
    <span class="text">{{ showText }}</span>
    <span class="count">{{ count }}</span>


  </div>
</template>

<script>
export const TYPE_TODAY = 1
export const TYPE_TODO = 2
export const TYPE_ALL = 3
// 只有通过 export default 导出的组件，才能被其他文件通过 import 引入使用
export default {
  //用于接收父组件传递的参数
  props: {
    cardType: {
      type: Number,
      default: TYPE_TODAY,
    },
    isSelected: {
      type: Boolean,
      default: false,
    },
    count: {
      type: Number,
      default: 0,
    }
  },
  name: 'CardItem',
  // 数据定义部分
  data() {
    return {
      type: 1,
    }
  },
  computed: {
    imgsrc() {
      let iconName
      switch (this.cardType) {
        case TYPE_TODAY:
          iconName = 'ic_today'
          break
        case TYPE_TODO:
          iconName = 'ic_plan'
          break
        case TYPE_ALL:
          iconName = 'ic_all'
          break
      }
      // return `@/assets/svg/${iconName + (this.isSelected ? '_selected' : '')}.svg`@只在import导入时可以用
      return `src/assets/svg/${ iconName + (this.isSelected ? '_selected' : '') }.svg`
    },
    showText() {
      switch (this.cardType) {
        case TYPE_TODAY:
          return '今天'
        case TYPE_TODO:
          return '计划'
        case TYPE_ALL:
          return '全部'
      }
    },
// 用于动态生成CSS类名对象。
    classObj() {
      return {
        selected: this.isSelected,           // 根据isSelected prop决定是否添加'selected'类
        unselected: !this.isSelected,        // 根据isSelected prop决定是否添加'unselected'类
        today: this.cardType === TYPE_TODAY, // 根据cardType prop决定是否添加'today'类
        plan: this.cardType === TYPE_TODO,   // 根据cardType prop决定是否添加'plan'类
        all: this.cardType === TYPE_ALL,     // 根据cardType prop决定是否添加'all'类
      }
    }

  },
}
  
</script>
<style scoped lang="scss">
.card-layout { 
  padding: 8px;
  border-radius: 12px;
  background: #cbcbcb;
  position: relative;
  color: #4c4c4c;

  .circle-icon {
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 50%;
    width: 24px;
    height: 24px;
  }
  img{
    width: 16px;
    height: 16px;
  }
  .circle-icon.today {
    background-color: var(--todo-blue);
  }
  .count{
    font-weight: bold;
    color: inherit;
    font-size: 16px;
    right: 12px;
    position: absolute;
    top: 8px;
  }
  .text{
    font-size: 14px;
    margin-top: 2px;
    color: inherit;
    font-weight: normal;
  }
}
.card-layout.selected {
  color: white;
  .circle-icon {
    background-color: white;
  }
}
//图片
.card-layout.today.unselected .circle-icon {
  background-color: var(--todo-blue);
}
.card-layout.plan.unselected .circle-icon {
  background-color: var(--todo-red);
}
.card-layout.all.unselected .circle-icon {
  background-color: var(--todo-gray);
}
//文字
.card-layout.selected.today {
  background-color: var(--todo-blue);
}

.card-layout.selected.plan {
  background-color: var(--todo-red);
}

.card-layout.selected.all {
  background-color: var(--todo-gray);
}
.card-layout:hover {
  background-color: #b7b7b7;
}
</style>
