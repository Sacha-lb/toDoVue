<template>
    <div id="toDoCard">
        <section>
            <p>{{date}}</p>
            <h1>ToDo List</h1>
            <p>{{listTasks.length}}</p>
        </section>
        
        <NewToDo @newTask="stockTasks"  />
      
            
        <ToDoList @delete="delleteTask" v-for="(task,index) in listTasks" :key="task" :id="index" :title="task.name" />
  
    </div>
    
</template>

<script>
    import NewToDo from '@/components/NewToDo'
    import ToDoList from '@/components/ToDoList'
    export default {
        name: 'App',
        components: {
            NewToDo,
            ToDoList
        },
        data(){
            return {
                listTasks: []
            }
        },
        props: [
            'title'
        ],
        computed:{
            date: function(){
                const now = new Date()
                const day = now.toLocaleString("default", { weekday : "long"})
                const dayNumber = now.getDay()
                const month = now.toLocaleString("default", {month: "long"})
                return `${day}  ${dayNumber}  ${month}`
            }
        },
        methods:{
            stockTasks(info){
                this.listTasks.push({name: info})
                console.log(this.listTasks)
            },
            delleteTask(data){
                console.log(data)
                this.listTasks.splice(data, 1)
            }
        }
    }
</script>

<style>
    
#toDoCard{
    padding: 15px;
    margin: 0 auto;
    padding-top: 50px;
    background-color: white;
    border-radius: 15px;
}



#toDoCard section{
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
    padding: 15px;
}
section p,h1{
    margin: 15px;
}


</style>


