<template>
    <div class="wrapper">
        <h4 style="margin: 5px 0 0 0;">Номер задачи: {{ task.id }}, Приоретет - {{ task.priority }}</h4>
        <p class="task-body">{{ task.body }}</p>
    </div>
</template>

<script>
    export default {
        props: {
            task: {
                type: Object,
                required: true
            }
        }
    }
</script>

<style scoped>
.wrapper{
    background-color: rgb(218, 218, 218);
    border: 3px solid black;
    border-radius: 5px;  
    margin-bottom: 15px;
    padding: 10px;
}
.task-body {
    white-space: normal;
    word-break: break-all;
}
</style>