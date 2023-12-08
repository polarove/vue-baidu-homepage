<template>
  <div
    class="wrapper"
    :style="{ width: props.width + 'px', height: props.height + 'px' }"
  >
    <div class="icon">
      <img :src="props.icon" id="alert" />
    </div>
    <div class="info">
      <span>{{ props.info }}</span>
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  width: {
    type: Number,
    required: true,
    default: '160'
  },
  height: {
    type: Number,
    required: true,
    default: '160'
  },
  info: {
    type: String,
    required: true,
    default: '暂无数据'
  },
  icon: {
    type: String,
    required: false,
    default:
      'https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=4160404059,3510095719&fm=179&app=35&f=PNG?w=152&h=152&s=4B011B62C7C2A4A561BFC59A03008093'
  }
})
</script>

<style lang="scss" scoped>
.wrapper {
  position: relative;
  .icon {
    position: absolute;
    top: 0;
    left: 0;
  }
  .info {
    position: absolute;
    top: 122px;
    left: 0;
    width: 100%;
    height: 100%;
    text-align: center;
    span {
      color: #9195a3;
    }
  }
}
</style>
