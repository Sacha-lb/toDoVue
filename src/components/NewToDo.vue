<template>
    <div class="create">
        <input v-model="taskToAdd" type="text" name="" id="">
        <a @click="addTask" class="button is-black">Ajouter !</a>
    </div> 
</template>




<script>
export default {
    data(){
        return{
            taskToAdd: null
        }
    },
    methods:{
        addTask(){
            this.$emit('newTask', this.taskToAdd)
        }
    }
  
}
</script>


<style>
.create{
    display: flex;
    flex-direction: row;
}
.create input,a{
    margin: 15px;
}
</style>
