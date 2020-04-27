<template>
  <div class="typeList_wrap clearfix">
    <ul class="clearfix">
      <li @click="getDataFromService" class="tab-active">全部户型 (6)</li>
      <li>二居 (4)</li>
      <li>三居 (4)</li>
    </ul>
    <div class="typelist clearfix">
      <div class="typelist-item">
        <a href="">
          <div class="typelistItem-left">
            <img src="https://s2.ifengimg.com/2016/04/29/21235f6e076fe4dd33c57e80763cf184.png" alt="">
          </div>
          <div class="typelistItem-right">
            <h4>中海寰宇天下 -C3-2室2厅1卫-88㎡(建面)</h4>
            <span class="price-item">520万元/套 <em class="default-wrod">参考总价</em></span>
          </div>
        </a>
      </div>
      <div v-if="type==1">
        {{fullName}}
      </div>
      <div v-else-if="type==2" @click="fullName">
        b
      </div>
      <div v-else>
        c
      </div>
    </div>
  </div>
</template>
<script>
import axios from 'axios'
import jsonpAdapter from 'axios-jsonp'
import $ from 'jquery'

const jsonp = require('jsonp')

console.log(axios, jsonpAdapter, $)

export default {
  name: 'TypeList',
  data() {
    return {
      type: 2,
      timer: null
    }
  },
  computed: {},
  methods: {
    getDataFromService() {
      // console.log(1234)
      clearTimeout(this.timer)
      this.timer = setTimeout(() => {
        console.log('调接口！！！')
      }, 300)
    },
    fullName: function() {
      // this.type=3,
      // this.axios.get('/proxy/sale/search/guide',
      // {
      //     params: {
      //         // dictId:101575,
      //         // page:1,
      //         // houseType:3
      //         city:3066,
      //         prefix: ''
      //     }
      // })
      // .then(response => (console.log(response.data)))
      // .catch(function (error) { // 请求失败处理
      //     console.log(error);
      // });
      // this.axios({
      //   url: 'https://house.ifeng.com/sale/search/guide',
      //   adapter: jsonpAdapter,
      //   callbackParamName: 'c'
      // })
      //   .then(res => {
      //     console.log(res)
      //   })
      //   .catch(res => {
      //     console.log(res)
      //   })
      let result = jsonp(
        'https://house.ifeng.com/sale/search/guide?city=3066,',
        {
          param: 'jsoncallback'
        },
        (err, data) => {
          console.log(data)
        }
      )

      // $.ajax({
      //   url: 'https://house.ifeng.com/sale/search/guide',
      //   type: 'GET',
      //   data: {
      //     city: 3066
      //   },
      //   xhrFields: {
      //     withCredentials: true
      //   },
      //   crossDomain: true,
      //   dataType: 'jsonp',
      //   jsonp: 'jsoncallback'
      //   // jsonpCallback: 'back'
      // })
      //   .done(res => {
      //     console.log(res)
      //   })
      //   .fail(function(err) {
      //     console.log(err)
      //   })
    }
  }
}
</script>
<style lang="scss">
@import './typelist';
</style>
