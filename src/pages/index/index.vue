<template>
  <div>

      <swiper
      :indicator-dots="indicatorDots"
      :autoplay="autoplay"
      :interval="interval"
      :duration="duration"
    >
      <block v-for="img in imgUrls" :key="img">
        <swiper-item>
          <image :src="img" style="width:100%" />
        </swiper-item>
      </block>
    </swiper>



    <i-grid i-class="no-border">
    <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>
        <i-grid-label>{{grid.title}}</i-grid-label>
    </i-grid-item>
    
  </i-grid>
  <i-panel title="最新消息">
    <view style="padding: 15px;">
      <i-card @click="goTo(item)" v-for="item in top" :key="item" i-class="split" :extra="item.name" :thumb="item.image">
         <view slot="content">{{item.remark}}</view>
         <view slot="footer">{{item.time}}</view>
      </i-card>
    </view>
  </i-panel>
  </div>
</template>

<script>
export default {
  data () {
    return {
      title_name:"最新消息",
      grids:[
        
        {title:"科目一",image:"/static/images/2.png"},
        {title:"科目二",image:"/static/images/3.png"},
        {title:"科目三",image:"/static/images/4.png"},
        {title:"科目四",image:"/static/images/5.png"},
      ],
      top:[
        {name:"元旦活动",time:"2020.01.01",image:"/static/images/lamp.png",remark:"新年新气象，为庆元旦，宏达驾校现推出特惠活动，即日起报名至1月10日，享特惠价2500元！"},
        {name:"圣诞节活动",time:"2019.12.25",image:"/static/images/shengdanjie-lingdang.png",remark:"叮叮当，叮叮当！宏达驾校和圣诞老人一起来送礼啦！即日起报名至12月31日，前25名享特惠价2500元！"},
        {name:"万圣节活动",time:"2019.11.01",image:"/static/images/witcheshat.png",remark:"不给糖就捣蛋！宏达驾校现推出万圣节特惠活动，凡报名即可参与抽奖，欢乐谷门票拿到手软！"},
        {name:"情人节活动",time:"2019.02.14",image:"/static/images/calendar.png",remark:"又是一年情人节，宏达驾校给情侣们送福利啦！即日起两人组团报名至2月20日，学费立减500！"},
      ],
      imgUrls:[
        '/static/images/01.jpg',
        '/static/images/02.jpg',
        '/static/images/03.jpg'
      ]
    }
  },

  methods: {
    goType(type){
      console.log(type)      
      let url = '../list/main?type=' + type.title
      mpvue.navigateTo({ url })
    },
    goTo(type){
    console.log(type)      
      let url = '../list/main?type=' + type.name
      mpvue.navigateTo({ url })
    }
  },

  

  created () {
  }
}
</script>

<style scoped>
div >>> .no-border {
  border-width: 0pt;
}
div >>> .split {
  margin-bottom: 10pt;
}
</style>
