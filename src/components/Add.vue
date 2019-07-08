<template>
  <div>
    <input type="text" @input="handleInput" v-model="user.name" />
    <input type="text"  v-model="user.say"/>
    <button @click="addItem">确定</button>
  </div>
</template>

<script>
export default {
    name: 'add',
    data(){
        return {
            user:{
                name:'',
                say:''
            }

        }
    },
    methods:{
        handleInput(event){
            let value = event.target.value
            this.$emit('input',value)
        },
        addItem(){
          let user = this.user
            this.$emit('setUser',user)
        }
    }
}
</script>

<style scoped>

</style>
