<script>
import HeaderComponent from '@/components/HeaderComponent.vue'
import TaskList from '@/components/TaskList.vue'
import CreateTaskForm from '@/components/CreateTaskForm.vue'

export default {
  components : {
    HeaderComponent, TaskList, CreateTaskForm
  },
  data() {
    return {
      todoList: [
        {id: 1, title: "Дело 1", desc: "Описание 1", complete: false},
        {id: 2, title: "Дело 2", desc: "Описание 2", complete: false},
        {id: 3, title: "Дело 3", desc: "Описание 3", complete: false}
      ]
    }
  },
  methods: {
    createTask(task) {
      this.todoList.push(task);
    },
    removeTask(task) {
      this.todoList = this.todoList.filter(t => t.id != task.id)
    },
    taskComplete(task) {
      if(this.todoList.filter(t => t.id === task.id)){
        task.complete = true
      };
      console.log(this.todoList)
    }
  }
}
</script>

<template>
  <header class="header">
    <HeaderComponent/>
  </header>
  <main class="main">
    <section class="wrapper">
      <TaskList 
        v-bind:TaskList="todoList"
        @remove="removeTask"
        @complete="taskComplete"
      />
    </section>
    <section class="create-task">
      <h2 class="create-task__title">
        Добавить задачу
      </h2>
      <CreateTaskForm
        @create="createTask"
      />
    </section>
  </main>
</template>

<style scoped>
  .header{
    max-width: 1280px;
    margin: 0 auto;
    padding: 25px 0 75px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .wrapper {
    max-width: 920px;
    width: 100%;
    margin: 0 auto;
    padding: 25px 60px;
    border-radius: 50px;
    background-color: rgba(150, 164, 117, 0.304);
  }

  .main {
    padding-bottom: 40px;
  }

  .create-task {
    max-width: 920px;
    width: 100%;
    margin: 0 auto;
    margin-top: 40px;
    padding: 25px 60px;
    border-radius: 50px;
    background-color: rgba(150, 164, 117, 0.304);
  }

  .create-task__title {
    margin: 0;
    margin-bottom: 30px;
    text-align: center;
    font-size: 28px;
    font-weight: 700;
    color: #3b6486;
  }
</style>
