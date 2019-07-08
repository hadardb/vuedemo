<template>
  <div>
    <input type="checkbox" name="all" v-model="selectAllstate"/>
    <span>已选中{{selectNum}}/全部{{items.length}}</span>
    <button @click="delItems" v-show="selectNum">删除已完成任务</button>
  </div>
</template>

<script>
export default {
  name: 'Todofooter',
    props:['items','selectNum','selectAllItems','delItems'],
    computed:{
      selectAllstate:{
        get: function() {
          return this.selectNum===this.items.length
        },
          set:function(value){
              this.selectAllItems(value)
          }
      }
    }
}
</script>

<style scoped>

</style>
