<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Add  v-model="textValue" @setUser="setUser" />
    {{textValue}}
    <List :items="items" :delItems="delItems"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Add from '@/components/Add.vue'
import List from '@/components/List.vue'

export default {
    name: 'home',
    data(){
        return{
            textValue: '',
            items:[
                {
                    name: '小王',
                    say: 'ok'
                },
                {
                    name: '小李',
                    say: 'no ok'
                },
                {
                    name: '小黄',
                    say: 'okkk'
                }
            ]
      }
    },
    methods:{
        setUser(data){
            this.items.push(data)
        },
        delItems(index){
            this.items.splice(index,1)
        }
    },
    components: {
        HelloWorld,
        Add,
        List
  }
}
</script>
