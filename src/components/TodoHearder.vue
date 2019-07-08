<template>
  <div>
    <input type="text" @keyup.enter="adds" v-model="like"/>
  </div>
</template>

<script>
export default {
  name: 'todoHearder',
    props:['addItem'],
    data(){
      return{
          like:''
      }
    },
    methods:{
      adds:function(){
         var { addItem, like } = this
          addItem(like)
          this.like= ''
      }
    }
}
</script>

<style scoped>

</style>
