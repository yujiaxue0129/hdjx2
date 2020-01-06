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

     <swiper indicator-dots="indicatorDots"
        autoplay="autoplay" interval="interval" duration="duration">
        <block wx:for="background" wx:key="*this">
          <swiper-item>
            <view class="swiper-item item"></view>
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
  <i-panel title="title_name">
    <view style="padding: 15px;">
      <i-card @click="tiao(item)" v-for="item in top" :key="item" i-class="split" :extra="item.name" :thumb="item.image">
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
        {name:"元旦活动",time:"2020.01.01",image:"/static/images/lamp.png",remark:"消息"},
        {name:"圣诞节活动",time:"2019.12.25",image:"/static/images/shengdanjie-lin.png",remark:"消息"},
        {name:"万圣节活动",time:"2019.11.01",image:"witcheshat.png",remark:"消息"},
        {name:"情人节活动",time:"2019.02.14",image:"calendar.png",remark:"消息"},
      ],
      imgUrls:[
        ""
      ]
    }
  },

  methods: {
    goType(type){
      console.log(type)      
      let url = '../list/main?type=' + type.title
      mpvue.navigateTo({ url })
    }
  },
   tiao(type){
    console.log(type)      
      let url = '../map/main'
      mpvue.navigateTo({ url })
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
