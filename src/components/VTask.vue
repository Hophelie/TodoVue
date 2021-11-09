<template>
<div class="grid justify-items-center">
    <div :class="`task--${completed} w-1/2 grid justify-items-center m-3 bg-purple-100 rounded-lg p-5`" :id="task.id" @click="onClick">
        <button class="delet text-gray-200 grid justify-self-end font-extrabold" @click.stop="onDelete()">X</button>
        <p class="task--title font-extrabold text-xl">{{task.title}}</p>
        <p>{{task.place}} - {{task.time}}</p>
        <p class="task__description">{{task.description}}</p>
    </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            completed:true
        }
    },
    methods:{
        onClick(){
            this.completed = !this.completed
        },
        onDelete(){
            this.$emit('delete', this.task.id)
        }
    },
    props: ['task','tasks'],
}
</script>

<style scoped>
.task{
    margin:12px;
}
.task--false {
    opacity: 0.5;
    text-decoration: line-through;
}

.list-item {
  display: inline-block;
  margin-right: 10px;
}
.list-enter-active, .list-leave-active {
  transition: all 1s;
}
.list-enter, .list-leave-to{
  opacity: 0;
  transform: translateY(30px);
}
</style>