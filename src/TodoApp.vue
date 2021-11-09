<template>
    <div class="TodoApp">
        <MonFormulaire :tasks="tasks" @submit="toggleForm"></MonFormulaire>
        <MaTache  v-for="task in tasks" :key="task.id" :task="task" @delete="onDelete"></MaTache>
    </div>
</template>

<script>

import MonFormulaire from './components/VFrom.vue'
import MaTache from './components/VTask.vue'

export default{
    data(){
        return{
            tasks:[]
        }
    },
    components:{
        MaTache,
        MonFormulaire
    },
    methods:{

        onDelete(index){
            const id = this.tasks.findIndex((task) => task.id === index)
            this.tasks.splice(id,1)
        },
    }
}
</script>