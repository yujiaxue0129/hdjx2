<template>
  <div>
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
      <i-card v-for="item in top" :key="item" i-class="split" :extra="item.subject" :thumb="item.image">
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
        {title:"消息",image:"/static/images/1.png"},
        {title:"科目一",image:"/static/images/2.png"},
        {title:"科目二",image:"/static/images/3.png"},
        {title:"科目三",image:"/static/images/4.png"},
        {title:"科目四",image:"/static/images/5.png"},
      ],
      top:[
        {subject:"科目",time:"时间1",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"消息"},
        {subject:"科目",time:"时间2",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"消息"},
        {subject:"科目",time:"时间3",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"消息"},
        {subject:"科目",time:"时间4",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"消息"}
      ],
    }
  },

  methods: {
    goType(type){
      console.log(type)      
      let url = '../list/main?type=' + type.title
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
