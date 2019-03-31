<template>
    <div class="tab">
        <button @click="clickHandle(item.id)" :key='item.id' v-for='item in listData'>{{item.title}}</button>

        <div :class="{active:currenIndex === item.id}" :key='item.id' v-for='item in listData'>{{item.content}}</div>
    </div>
</template>
<script>
export default {
  data() {
    return {
      currenIndex: 1,
      listData: [
        {
          id: 1,
          title: "苹果",
          content: "apple"
        },
        {
          id: 2,
          title: "香蕉",
          content: "banana"
        },
        {
          id: 3,
          title: "橘子",
          content: "orange"
        }
      ]
    };
  },
  methods: {
    clickHandle(id) {
      this.currenIndex = id;
    }
  }
};
</script>
<style>
.tab {
  width: 750rpx;
  height: 375rpx;
  background-color: #eee;
}
.tab button {
  width: 200rpx;
  display: inline-block;
}
.tab div {
  width: 740rpx;
  min-height: 305rpx;
  background-color: lightblue;
  display: none;
}
.tab .active {
  display: block;
}
</style>

