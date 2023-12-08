<template>
  <div id="seb">
    <div style="text-align: center">
      <img
        id="logo"
        src="https://www.baidu.com/img/PCtm_d9c8750bed0b3c7d089fa7d55720d6cf.png"
        height="129"
        width="270"
      />
      <form>
        <span id="search_bar_wrapper">
          <div class="i-ep-camera" id="camera"></div>
          <input id="search_bar" type="text" />
        </span>
        <span id="button">
          <input type="submit" value="百度一下" id="sb" />
        </span>
      </form>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
#seb {
  position: relative;
  height: 510px;
  width: 1000px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  #search_bar_wrapper {
    position: relative;
    width: 546px;
    text-align: left;
    #camera {
      position: absolute;
      top: -4px;
      right: 10px;
      font-size: 1.7rem;
      color: #767676;
    }
    #search_bar {
      width: 512px;
      height: 16px;
      padding: 12px 16px;
      font-size: 16px;
      margin: 0;
      vertical-align: top;
      outline: 0;
      box-shadow: none;
      border-radius: 10px 0 0 10px;
      border-left: 2px solid #c4c7ce;
      border-top: 2px solid #c4c7ce;
      border-bottom: 2px solid #c4c7ce;
      border-right: 0;
      background: #fff;
      color: #222;
      overflow: hidden;
      box-sizing: content-box;
      -webkit-tap-highlight-color: transparent;
    }
  }
  #button {
    width: 108px;
    height: 44px;
    position: relative;
    z-index: 2;
    #sb {
      cursor: pointer;
      width: 108px;
      height: 44px;
      line-height: 45px;
      padding: 0;
      background: 0 0;
      background-color: #4e6ef2;
      border-radius: 0 10px 10px 0;
      font-size: 17px;
      color: #fff;
      box-shadow: none;
      font-weight: 400;
      border: none;
      outline: 0;
    }
  }
}
</style>
