<template>
  <div class="info_container">
    <div class="news_list">
      <div style="display: flex; justify-content: space-between">
        <div>
          <span
            class="menu_item"
            :class="{ active: !flag }"
            @click="toggleActiveMenu(0)"
            >我的关注 <span class="underline"></span
          ></span>
          <span
            class="menu_item"
            :class="{ active: flag }"
            @click="toggleActiveMenu(1)"
          >
            推荐
            <span class="underline"></span>
          </span>
        </div>
        <div v-if="!flag" flex="~" items-center>
          <div class="i-ep-plus inline-block"></div>
          &nbsp;&nbsp;
          <span>自定义</span>
        </div>
      </div>
      <div v-if="flag">
        <newsVue
          v-for="(item, index) in news"
          :url="item.url"
          :image="item.image"
          :title="item.title"
          :datetime="item.datetime"
          :publisher="item.publisher"
          :key="index"
          @click="handleClick(item.url)"
        >
        </newsVue>
      </div>
      <div v-else>
        <subscribedVue edVue></subscribedVue>
      </div>
    </div>
    <div class="trending_search" v-if="flag">
      <div flex="~" justify-between>
        <div flex="~" items-center hover-color-blue cursor-pointer>
          <span class="text-size-[1.2rem] font-bold inline-block"
            >百度热搜
          </span>
          <div class="i-ep-arrow-right inline-block text-size-[1.3rem]"></div>
        </div>
        <div flex="~" items-center hover-color-blue cursor-pointer>
          <div class="i-ep-refresh inline-block"></div>
          <span class="inline-block">换一换</span>
        </div>
      </div>
      <trendingsVue
        class="mt-10px"
        v-for="item in trendings"
        :order="item.order"
        :color="item.color"
        :title="item.title"
        :isHeated="item.isHeated"
      ></trendingsVue>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, reactive } from 'vue'
import newsVue from './news.vue'
import subscribedVue from './subscribed.vue'
import trendingsVue from './trendings.vue'
import { INews, ITrendings } from '../typings/index'

const flag = ref<number>(1)

const news = reactive<Array<INews>>([
  {
    image: 'https://avatars.githubusercontent.com/u/95893742?v=4',
    title: '我的Github主页',
    datetime: '2023-6-16 12:39',
    publisher: '页面作者 - 刘棋',
    url: 'https://github.com/polarove',
  },
  {
    image:
      'https://gimg3.baidu.com/search/src=http%3A%2F%2Fpics0.baidu.com%2Ffeed%2F37d3d539b6003af3ba1a4742eca093501138b683.jpeg%40f_auto%3Ftoken%3D40ccb9a2107bae03f4b1ce8abd4fe62b&refer=http%3A%2F%2Fwww.baidu.com&app=2021&size=f360,240&n=0&g=0n&q=75&fmt=auto?sec=1687021200&t=040b873422f7a5b00f9ca41f0833e62a',
    title: '基辛格称若局势升级台海或发生军事冲突，外交部回应',
    datetime: '2023-6-16 12:32',
    publisher: '北晚在线',
    url: 'https://www.baidu.com',
  },
  {
    image:
      'https://gimg3.baidu.com/search/src=http%3A%2F%2Fpics3.baidu.com%2Ffeed%2F500fd9f9d72a60598359bcc4c5866197013bbae6.jpeg%40f_auto%3Ftoken%3Da60307750ee863ae9ffdd82b276d308b&refer=http%3A%2F%2Fwww.baidu.com&app=2021&size=f360,240&n=0&g=0n&q=75&fmt=auto?sec=1687021200&t=e512974f1a08ee504e7cba59e5a63258',
    title: '国防部：加方在涉华问题上应谨言慎行',
    datetime: '2023-6-16 11:21',
    publisher: '每日经济新闻',
    url: 'https://www.baidu.com',
  },
  {
    image:
      'https://himg.bdimg.com/sys/portraitn/item/public.1.f4883e23.61hJkjpdGJHu8ylg9nOkGQ',
    title: '百度一下，你就知道',
    datetime: '2023-6-16 13:16',
    publisher: '北京日报客户端',
    url: 'https://www.baidu.com',
  },
])

const trendings = reactive<Array<ITrendings>>([
  {
    order: 0,
    color: '#f63051',
    title: '促销费多点开花 扩内需“快马加鞭”',
    isHeated: false,
  },
  {
    order: 1,
    color: '#fe2d46',
    title: '冲场拥抱梅西球迷被刑拘！',
    isHeated: false,
  },
  {
    order: 2,
    color: '#f60',
    title: '跳江救人小哥被奖励10万元和一套房',
    isHeated: true,
  },
  {
    order: 3,
    color: '#faa90e',
    title: '高考考生们这些“套路”骗局要当心',
    isHeated: false,
  },
  {
    order: 4,
    color: '#9195a3',
    title: '越南开始担心被“抢饭碗”了',
    isHeated: false,
  },
  {
    order: 5,
    color: '#9195a3',
    title: '杜江问梅西嗯哼的签名照是真迹吗',
    isHeated: false,
  },
  {
    order: 6,
    color: '#9195a3',
    title: '比尔盖茨回复黄晓明',
    isHeated: false,
  },
  {
    order: 7,
    color: '#9195a3',
    title: '连那英都接不住的场子',
    isHeated: false,
  },
  {
    order: 8,
    color: '#9195a3',
    title: '女子烈日下举牌球前夫复婚',
    isHeated: false,
  },
  {
    order: 9,
    color: '#9195a3',
    title: '什么？！我居然是大帅哥？',
    isHeated: true,
  },
])

const toggleActiveMenu = (index: number) => {
  flag.value = index
}

const handleClick = (url: string) => {
  window.open(url)
}
</script>

<style lang="scss" scoped>
.info_container {
  width: 100%;
  margin: 0 auto;
  position: relative;
  z-index: 0;
  min-width: 1000px;
  display: flex;
  justify-content: center;
  .active {
    color: #222 !important;
    .underline {
      display: block !important;
    }
  }
  .news_list {
    margin-right: 80px;
    .menu_item {
      position: relative;
      display: inline-block;
      color: #9195a3;
      cursor: pointer;
      margin-right: 24px;
      margin-top: 4px;
      line-height: 26px;
      user-select: none;
      margin-bottom: 10px;
      .underline {
        position: absolute;
        content: '';
        display: none;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 2px;
        background-color: #4e71f2;
        transition: all 0.3s ease-in-out;
      }
    }
  }
  .trending_search {
    margin-left: 80px;
  }
}
</style>
