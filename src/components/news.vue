<template>
  <div class="news">
    <div class="image_container ccc">
      <img :src="props.image" class="image" />
    </div>
    <div class="news_content ccc">
      <div class="content_body">{{ props.title }}</div>
      <div class="content_footer">
        {{ props.datetime }}&nbsp;&nbsp;&nbsp;{{ props.publisher }}
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  image: {
    type: String,
    required: true,
  },
  title: {
    type: String,
    required: true,
  },
  datetime: {
    type: String,
    required: true,
  },
  publisher: {
    type: String,
    required: true,
  },
  url: {
    type: String,
    required: true,
  },
})
</script>

<style lang="scss" scoped>
.news {
  margin: 20px 0;
  .ccc {
    display: inline-block;
  }
  &:hover {
    cursor: pointer;
    .image_container {
      box-shadow: 0 0 10px #ccc;
    }
    .content_body {
      color: #3195cf;
    }
  }
}

.image_container {
  width: 184px;
  height: 122px;
  border-radius: 15px;
  overflow: hidden;
  transition: all 0.2s ease-in-out;
  .image {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}
.news_content {
  position: relative;
  box-sizing: border-box;
  min-height: 123px;
  min-width: 300px;
  padding: 8px 0px 24px 10px;
  vertical-align: top;
  .content_body {
    font-size: 1.3rem;
    font-weight: 500;
    color: #333;
    line-height: 1.5;
    margin-bottom: 8px;
    max-width: 380px;
    word-wrap: break-word;
    word-break: break-all;
    text-overflow: ellipsis;
  }
  .content_footer {
    position: absolute;
    bottom: 0;
    right: left;
    font-size: 12px;
    color: #999;
  }
}
</style>
