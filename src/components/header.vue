<template>
  <div class="nav_wrapper">
    <div class="u-top-left">
      <a class="list_item u-top-left-item">新闻</a>
      <a class="list_item u-top-left-item">hao123</a>
      <a class="list_item u-top-left-item">地图</a>
      <a class="list_item u-top-left-item">贴吧</a>
      <a class="list_item u-top-left-item">视频</a>
      <a class="list_item u-top-left-item">图片</a>
      <a class="list_item u-top-left-item">网盘</a>
      <a class="list_item u-top-left-item">更多</a>
    </div>
    <div class="u-top-right">
      <div class="weather_wrapper u-top-right-item">
        <div class="weather_item">
          <span style="margin-right: 20px">福建</span>
          <img
            class="weather_icon"
            src="https://dss0.bdstatic.com/5aV1bjqh_Q23odCf/static/superman/img/weather/icons/a2.png"
            height="23"
            width="23"
          />
          <span class="degree">24°C</span>
          <div class="tag">
            <span class="type">优</span>
          </div>
        </div>
      </div>
      <div class="settings u-top-right-item">设置</div>
      <div class="avatar u-top-right-item">
        <span class="avatar_image">
          <img
            id="my_avatar"
            src="https://himg.bdimg.com/sys/portraitn/item/public.1.f4883e23.61hJkjpdGJHu8ylg9nOkGQ"
          />
        </span>
        <span class="username">AniBerzzzz</span>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
.nav_wrapper {
  width: 100%;
  display: flex;
  justify-content: space-between;

  .u-top-left {
    .list_item {
      color: #222;
      margin-right: 24px;
      margin-top: 19px;
      display: inline-block;
      position: relative;
      text-align: center;
    }
    .u-top-left-item {
      &:hover {
        color: #3385ff;
        cursor: pointer;
      }
    }
  }
  .u-top-right {
    display: flex;
    justify-content: space-between;
    align-items: center;
    .u-top-right-item {
      margin-right: 20px;
      &:hover {
        color: #3385ff;
        cursor: pointer;
      }
      .weather_item {
        display: flex;
        justify-content: space-between;
        align-items: center;
        .weather_icon {
          background-size: 100% 100%;
          margin-right: 4px;
          display: inline-block;
        }
        .degree {
          display: inline-block;
        }
        .tag {
          margin-left: 4px;
          .type {
            border-radius: 9px;
            background-color: #40c057;
            color: #fff;
            font-size: 11px;
            display: inline-block;
            line-height: 17px;
            text-align: center;
            padding: 0 6px;
          }
        }
      }
      .avatar_image {
        position: relative;
        width: 30px;
        height: 30px;
        border: 1px solid #4e71f2;
        display: inline-block;
        border-radius: 50%;

        #my_avatar {
          padding: 2px;
          width: 28px;
          height: 28px;
          border-radius: 50%;
        }
      }
      .username {
        display: inline-block;
        max-width: 100px;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
        -o-text-overflow: ellipsis;
        vertical-align: top;
        margin-top: 3px;
        margin-left: 6px;
        color: #000;
      }
    }
    .avatar {
      &:hover {
        .username {
          color: #3385ff;
          cursor: pointer;
        }
      }
    }
  }
}
</style>
