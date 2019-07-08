<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <TodoHearder :addItem="addItem" />
    <TodoBody :items="items" :delItem="delItem" :selectNum="selectNum"/>
    <TodoFooter :items="items" :selectNum="selectNum" :delItems="delItems" :selectAllItems="selectAllItems"/>
  </div>
</template>

<script>
// @ is an alias to /src
import TodoHearder from '@/components/TodoHearder.vue'
import TodoBody from '@/components/TodoBody.vue'
import TodoFooter from '@/components/TodoFooter.vue'

export default {
    name: 'home',
    data(){
        return{
            items:[
                {
                    id: 0,
                    name: '吃饭',
                    value: true
                },
                {
                    id: 1,
                    name: '睡觉',
                    value: false
                },
                {
                    id: 2,
                    name: '打豆豆',
                    value: false
                },
            ],
      }
    },
    methods:{
       addItem(item){
           item && this.items.push({id: this.items.length ,name: item,value: false})
       },
        delItem(index){
           this.items.splice(index,1)
        },
        // 删除所有勾选
        delItems(){
           this.items = this.items.filter((item)=> !item.value)
        },
        // 全选/全不选
        selectAllItems(select){
           this.items.forEach((e)=> e.value=select)
        }
    },
    computed:{
        selectNum: function (){
            return this.items.reduce((total,currentValue)=> total + (currentValue.value ? 1 : 0),0)
        }
    },
    components: {
        TodoHearder,
        TodoBody,
        TodoFooter
  }
}
</script>
