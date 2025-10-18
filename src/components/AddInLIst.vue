<template>
    <div>
        <h2>Добавить задачу</h2>
            <div class="wrapper">
                <input v-model="body" class='input' placeholder="Введите описание задачи">
                    
                    <select name="priority" class="priority" v-model="priority">
                        <option value="Без приоретета" selected>Без приоретета</option>
                        <option value="Высший" style="color: #a83b3b;">Высший приоретет</option>
                        <option value="Средний" style="color: #dbd758;">Средний приоретет</option>
                        <option value="Низший" style="color: #3ba85a;">Низший приоретет</option>
                    </select>

                <button class="button" @click="addTask">Добавить</button> 
            </div>
    </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';
    export default {
        data() {
            return {
                body: '',
                priority: "Без приоретета"
            };
    },
    methods: {
        addTask() {
            if (this.body.trim() === '') {
                alert('Введите описание задачи');
                return;
            }
            const newTask = {
                id: uuidv4(),
                body: this.body,
                priority: this.priority
            };
            this.$emit('task-added', newTask); 
            this.body = '';
            this.priority = "Без приоретета";
        }
    }
    }
</script>

<style scoped>
.wrapper{
    display: flex;
    flex-direction: column; 
    align-items: flex-start; 
    gap: 10px;
}
.input{
    width: 450px;
    padding: 10px;
    border: 2px solid black;
    border-radius: 5px;
    box-shadow: 2px 2px 5px rgb(71, 71, 71);
    cursor: pointer;
    transition: all 0.3s;
}
.priority{
    padding: 10px;
    border: 2px solid black;
    border-radius: 5px;
    box-shadow: 2px 2px 5px rgb(71, 71, 71);
    cursor: pointer;
    transition: all 0.3s;
}
.button{
    padding: 10px;
    border: 2px solid black;
    border-radius: 5px;
    box-shadow: 2px 2px 5px rgb(71, 71, 71);
    margin: auto;
    cursor: pointer;
    transition: all 0.3s;
}



.input:hover{
    transform: translateY(-3px);
}
.priority:hover{
    transform: translateY(-3px);
}
.button:hover{
    transform: translateY(-3px);
}
</style>