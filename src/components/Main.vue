<template>
<h2>To-Do-List</h2>
    <div class="main">
        <div class="text_in_modal_window">
            <AddInLIst style="margin-left: 20px;" @task-added="addTask"></AddInLIst>
                <h1>Задачи:</h1>
                <div>
                    <ul>
                        <li v-for="item in list" :key="item.id">
                            <List :task="item" style="margin-left: 30px;"></List>
                        </li>
                    </ul>
            </div>
        </div>
    </div>
</template>

<script>
import AddInLIst from './AddInLIst.vue';
import List from './List.vue';

    export default {
        components: {
            AddInLIst, List
        },
        data(){
            return{
                list: [{id:1, body:'Ноdsaaaaaadasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaadasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasasdsdsdsdsdsdsdмер 1', priority:'max'},
                    {id:2, body:'Номер 2', priority:'avg'},
                    {id:3, body:'Номер 3', priority:'min'},
                    {id:4, body:'Номер 4', priority:'max'},
                    {id:5, body:'Номер 5', priority:'avg'},
                ]
            }
        },
        methods: {
            addTask(newTask) {
                this.list.push(newTask); 
            }
    }

    }
</script>

<style scoped>
.main{
    display: flex;
    justify-content: center; 
    align-items: center;
    position: fixed;
    margin: -10px 0 0 20px;
    position: absolute;
    flex-direction: column;
    min-width: 60%;
    min-height: 80vh;
    max-width: 60%;
    border: 2px solid black;
    border-radius: 15px;
    box-shadow: 10px 5px 5px rgb(71, 71, 71);
    overflow-y: auto;
}
.text_in_modal_window{
    justify-content: flex-start; 
    align-items: flex-start;
    position: absolute;
    top: 0;
    left: 25px;
    
}
</style>