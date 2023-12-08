<template>
  <div class="card">
    <span>我的导航</span>
    <emptyVue class="empty"></emptyVue>
    <div id="add">点击添加</div>
    <div class="site_list"></div>
  </div>
</template>

<script setup lang="ts">
import emptyVue from './empty.vue'
</script>

<style lang="scss" scoped>
.card {
  position: relative;
  width: 1120px;
  height: 256px;
  box-sizing: border-box;
  background: rgba(255, 255, 255, 0.4);
  border: 1px solid rgba(0, 0, 0, 0.05);
  box-shadow: 0 2px 8px 0 rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  padding: 12px;
}
.empty {
  width: 100%;
  height: 100%;
  position: absolute;
  left: 50%;
  top: 40%;
  transform: translate(-50%, -50%);
}
#add {
  position: absolute;
  border-radius: 8px;
  left: 50%;
  width: 80px;
  height: 30px;
  top: 193px;
  line-height: 30px;
  color: #333333;
  cursor: pointer;
  transform: translate(-50%, 0);
  background: #f5f5f6;
  text-align: center;
}
</style>
