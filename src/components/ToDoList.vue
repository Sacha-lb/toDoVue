<template>

        <span class="list">
            <input v-model="check" type="checkbox" name="" id="">
            <p :class="{isCheck: check}">{{title}}</p>
            <a @click="deleteTask(id)" class="button is-danger">Supprimer</a>
        </span>
        
</template>




<script>
export default {
   name: 'App',

        props:{
            title: String,
            id: Number
        },
    data(){
            return {
                check: null
            }
        },
    methods:{
        deleteTask(id){
            this.$emit('delete', id)
        }
    }
}
</script>


<style>
.list{
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
    padding: 20px;
}

.isCheck{
    text-decoration-line: line-through;
}



</style>
