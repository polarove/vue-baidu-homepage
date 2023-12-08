<template>
  <div>
    <span v-if="!props.order">
      <div
        class="i-ep:download rotated inline-block text-size-16px mr-4px"
        :style="{ color: props.color }"
      ></div>
      <span class="title">{{ props.title }}</span>
    </span>

    <span v-else>
      <span class="order" :style="{ color: props.color }">{{
        props.order
      }}</span>
      <span class="title">{{ props.title }}</span>
    </span>
    <span v-if="props.isHeated" class="hot">热</span>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  order: {
    type: Number,
  },
  color: {
    type: String,
  },
  title: {
    type: String,
  },
  isHeated: {
    type: Boolean,
    default: false,
  },
})
</script>

<style lang="scss" scoped>
.rotated {
  transform: rotate(180deg);
}
.order {
  font-size: 16px;
  margin-right: 10px;
}
.title {
  font-size: 16px;
  color: #222222;
  cursor: pointer;
  &:hover {
    color: #3195cf;
  }
}
.hot {
  display: inline-block;
  padding: 0 2px;
  text-align: center;
  vertical-align: middle;
  font-style: normal;
  color: #fff;
  overflow: hidden;
  line-height: 16px;
  height: 16px;
  font-size: 12px;
  border-radius: 4px;
  font-weight: 200;
  background-color: #f60;
}
</style>
