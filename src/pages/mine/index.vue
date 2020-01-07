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
  

    <view style="padding: 15px;">
      <i-card @click="tiao(item)" v-for="item in top" :key="item" i-class="split" :extra="item.name" :thumb="item.image">
         <view slot="content">{{item.remark}}</view>
         <view slot="footer">{{item.time}}</view>
      </i-card>
    </view>

  </div>
</template>


<script>
export default {
  data () {
    return {
      title_name:" ",
      top:[
        {title:"我的收藏",image:"/static/images/2.png"},
        {title:"联系客服",image:"/static/images/3.png"},
        {title:"科目三",image:"/static/images/4.png"},
        {title:"科目四",image:"/static/images/5.png"},
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



<script>
export default {
  data () {
    return {
    }
  },

  methods: {
 
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
</style>