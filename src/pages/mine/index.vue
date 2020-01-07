<template>
  <div>
    <view class="userinfo">
    <view class="userinfo-avatar">
    <open-data type="userAvatarUrl"></open-data>
    </view>
    <open-data type="userNickName"></open-data>
    </view>
  

    <i-grid i-class="no-border">
      <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>
        <i-grid-label>{{grid.title}}</i-grid-label>
      </i-grid-item> 
  </i-grid>
<p>  </p>
<p>  </p>
<p>  </p>
 <i-panel title="您对我们驾校的建议：">
      <i-input :value="name" @change="changeName($event)" title="类别" autofocus placeholder="服务、价格、活动等" maxlength="20" />
      
      <i-input :value="reason" @change="changeReason($event)" title="建议" placeholder="请输入对我们的建议" maxlength="50" />
    </i-panel>
    <i-button @click="handleClick" type="warning" :ghost="true" shape="circle" size="small" >提交</i-button>
    

  </div>
</template>


<script>
export default {
  data () {
    return {
      title_name:" ",
       grids:[
        
        {title:"收藏",image:"/static/images/收藏.png"},
        {title:"客服",image:"/static/images/客服.png"},
        {title:"预约",image:"/static/images/预约.png"},
       
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
.userinfo {
  position: relative;
  width: 750rpx;
  height: 320rpx;
  color: #666;
  display: flex;
  flex-direction: column;
  align-items: center;
}
 
.userinfo-avatar {
  overflow:hidden;
  display: block;
  width: 160rpx;
  height: 160rpx;
  margin: 20rpx;
  margin-top: 50rpx;
  border-radius: 50%;
  border: 2px solid #fff;
  box-shadow: 3px 3px 10px rgba(0, 0, 0, 0.2);
}
.tips {
  padding: 20pt;
  font-size: 10pt;
  color:lightblue;
}
</style>