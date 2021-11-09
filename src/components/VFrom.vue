 <template>  
 <div class="grid justify-items-center m-5"> 
        <form ref="myForm" class=" relative flex flex-col w-1/3 " @submit.prevent="onSubmit" >
            <input type="text" name="task" class="bg-indigo-50 rounded-lg m-1 p-3" v-model="form.title">
            <input type="date" name="date" class="bg-indigo-100 rounded-lg m-1 p-3"  v-model="form.time">
            <input type="text" name="lieu" class="bg-indigo-50 rounded-lg m-1 p-3" v-model="form.place">
            <input type="text" name="description"  class="bg-indigo-100 rounded-lg m-1 p-3"  v-model="form.description">
            <button class="valid btn btn-primary">Valider</button>
        </form>
    </div> 
 </template>

 <script>
    export default {
        data(){
            return{
                id:0,
                form:{
                    title:null,
                    place:null,
                    time:null,
                    description:null,
                    priority:null
                }
            }      
        },
        props: ['tasks'],
        
        methods:{
            onSubmit(){
                const task = {
                    ...this.form,
                    id:this.id
                }
                this.tasks.push(task)
                
                this.id++
                
            },
        },
        
    }
 </script>
