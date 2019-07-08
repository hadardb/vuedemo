<template>
  <ul>
    <Item v-for="(item,index) in items" :key="item.index" :item="item" :index="index" :delItems="delItems"/>

  </ul>
</template>

<script>
  import Item from "@/components/Item"
export default {
    name: 'List',
    props:['items','delItems'],
    components:{
        Item
    }
}
</script>

<style scoped>

</style>
