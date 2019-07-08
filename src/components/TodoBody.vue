<template>
  <div>
    <Item v-for="(item,index) in items" :key="index" :delItem="delItem" :item="item" :index="index" :selectNum="selectNum"/>
  </div>
</template>

<script>
  import Item from "@/components/TodoItem"
export default {
  name: 'TodoBody',
    props:['items','delItem','selectNum'],
    components:{
      Item
    }

}
</script>

<style scoped>

</style>
