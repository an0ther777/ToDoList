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
    background: (rgba(38, 38, 38, 1) 55%, rgba(61, 61, 61, 1) 100%);
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