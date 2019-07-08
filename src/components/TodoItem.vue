<template>
  <div class="item" @mouseenter="EnterItem" @mouseleave="LeaveItem">
    <input :id="checkId" type="checkbox" name="like" v-model="item.value">
    <label :for="checkId">{{index+1}}.{{item.name}}</label>
    <button @click="delItem(index)" v-show="isShow">删除该兴趣</button>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
    props:['item','index','delItem','selectNum'],
    data(){
      return {
          isShow:false,
          // checkId :''
      }
    },
    computed:{
        checkId: function(){
            return 'check' + this.index
        },

    },
    methods:{
      EnterItem(){
          this.isShow=true
      },
        LeaveItem(){
            this.isShow=false
        },
    }
}
</script>

<style scoped>
  .item{
  }
</style>
