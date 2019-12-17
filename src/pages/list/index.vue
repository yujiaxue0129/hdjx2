<template>
  <div>
      <i-card v-for="item in list" :key="item" i-class="split" :extra="item.subject" :thumb="item.image">
         <view slot="content">{{item.remark}}</view>
         <view slot="footer">{{item.time}}</view>
      </i-card>
  </div>
</template>

<script>
export default {
  data () {
    return {
      list:[]
    }
  },
  onLoad (option){
    
    this.list = require('@/data/' + option.type + '.json')
    console.log(this.list)
  },
  methods: {
 
  },

  created () {
  }
}
</script>

<style scoped>

</style>