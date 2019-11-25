# vue-full-page

## 介绍

vue全屏滑动组件(移动端、PC端(鼠标滚轮滑动)都已兼容) 

支持局部页面动画 附带示例demo

注意事项：本组件目前仅支持刷新初始化判断PC端和移动端环境、以及元素高度的初始化。

## 功能点

1.移动端全屏触摸滑动

2.pc端鼠标滚轮切换

3.页面切换动画重置

4.支持动画队列式出现

5.解决ios滑动页面回弹

6.扩展：自定义animate动画指令

## 示例

http://null_639_5368.gitee.io/v-full-page/#/

## 码云

https://gitee.com/null_639_5368/v-full-page

## 安装

yarn add mv-full-page

yarn add inobounce

按需使用动画指令：

拷贝utils/directives.js

yarn add animate.css

```
// main.js

import 'animate.css'
import directives from './utils/directives'
Vue.use(directives)

```

## 使用方法
```
import MVFullPage from 'mv-full-page'

<mv-full-page     :pages="4" // 全屏页面数量
                 :page.sync="currentPage"  // 当前页码
                 :bgArr="bgArr" // 页面背景数组> 
     <template #page1>  // 这里插槽必须按照page[number]的形式
        <div class="page1">
          <p v-animate="{
            name:'bounceInLeft'
          }">页面1 第一个动画</p>
          <p v-animate="{
            name:'bounceInLeft',
            delay:1
          }">页面1 第二个动画</p>
        </div>
      </template>
</mv-full-page>

import VFullPage from '@/components/VFullPage/index.vue'

export default {
  name: 'home',
  components: {
    VFullPage
  },
  data () {
    return {
      currentPage: 1,
      bgArr: ['cadetblue', 'orange', 'pink', 'green']
    }
  }
}
```

