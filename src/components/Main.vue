<template>
  <div class="container">
    <h2>To-Do-List</h2>
    <div class="main">
      <div class="content">
        <AddInList @task-added="addTask"></AddInList>
        <h1>Задачи:</h1>
        <ul>
          <li v-for="item in list" :key="item.id">
            <List :task="item"></List>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import AddInList from './AddInList.vue';
import List from './List.vue';

export default {
  components: {
    AddInList, 
    List
  },
  data() {
    return {
      list: [
        {id:1, body:'Задача 1', priority:'max'},
        {id:2, body:'Задача 2', priority:'avg'},
        {id:3, body:'Задача 3', priority:'min'},
        {id:4, body:'Задача 4', priority:'max'},
        {id:5, body:'Задача 5', priority:'avg'},
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
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 20px;
}

.main {
  width: 60%;
  min-height: 80vh;
  border: 2px solid black;
  border-radius: 15px;
  box-shadow: 4px 3px 5px rgb(71, 71, 71);
  padding: 20px;
  overflow-y: auto;
}

.content {
  width: 100%;
}

h2 {
  margin-bottom: 20px;
  text-align: center;
}

h1 {
  margin: 20px 0 10px 0;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  margin-bottom: 10px;
}
</style>