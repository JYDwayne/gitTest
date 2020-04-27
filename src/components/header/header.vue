
<template>
  <div class="main_head">
    <!-- 面包屑 start -->
    <div class="bread-crumbs">
      <span>
        <a href="">凤凰网房产 > </a><a href="">城市+楼盘 > </a> <a href=""> 区县+楼盘 > </a><a href=""> 楼盘名称 > </a>楼盘名称+户型
      </span>
    </div>
    <!-- 面包屑 end -->
    <!-- 头部 start -->
    <div class="houseTop-info">
      <div class="houseTop-img fl">
        <img src="data:image/png;base64,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" alt="">
      </div>
      <div class="houseTop-mess fr">
        <div class="houseTop-heade">
          <h4 class="fl">中海寰宇天下<em>别名：御山府、御山府</em></h4>
          <span class="tell-head fr">4008185005 - 48382</span>
        </div>
        <div class="head-label fl">
          <!-- 在售 in-sale 待售  for-sale  售罄 sold-out -->
          <span class="HeadeSales-status in-sale">在售</span>
          <span class="HeadeProperty-type">物业类型</span>
        </div>
        <p class="time-head fr"><em class="mr-10">2019年5月6日更新</em>纠错</p>
      </div>
    </div>
    <!-- 头部 end -->
    <type-list></type-list>
  </div>

</template>


<script>
import axios from 'axios'
import TypeList from '../typeList/typeList.vue'

//  console.log(axios)
export default {
  name: 'Header',
  // name:'Header'
  components: {
    TypeList
  }
}
</script>
<style lang="scss" socped>
@import './head';
</style>
