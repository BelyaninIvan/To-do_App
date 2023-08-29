<script>
import TaskItem from '@/components/TaskItem.vue'
 export default {
    components: {
        TaskItem
    },
    props: {
        TaskList: {
            type: Array,
            required: true
        }
    }
 }
</script>

<template>
    <h1 class="title">Список дел:</h1>
    <ul class="list">
        <TaskItem 
        v-for="task in TaskList"
        v-bind:task="task"
        />
    </ul>
</template>

<style scoped>
  .title {
    margin: 0;
    margin-bottom: 30px;
    text-align: center;
    font-size: 28px;
    font-weight: 700;
    color: #3b6486;
  }

  .list {
    display: flex;
    margin: 0;
    padding: 0;
    list-style-type: none;
    flex-direction: column;
    row-gap: 15px;
  }
</style>