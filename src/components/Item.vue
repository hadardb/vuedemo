<template>
  <li @click="deleteThis">
    {{item.name}}说{{item.say}}
  </li>
</template>

<script>
export default {
    name: 'Item',
    props:['item',"index","delItems"],
    methods:{
        deleteThis(){
            let {index, delItems} =this
            delItems(index)
        }
    }
}
</script>

<style scoped>

</style>
