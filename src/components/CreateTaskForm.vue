<script>
 export default {
    data() {
        return {
            task: {
                title: '',
                desc: ''
            }
            
        }
    },
    methods: {
        createTask() {
            this.task.id = Date.now();
            this.$emit('create', this.task);
            this.task = {
                title: '',
                desc: ''
            }
            
        }
    }
 }
</script>

<template>
<form class="form" @submit.prevent>
    <input 
        v-model="task.title"
        class="form__input" 
        type="text" 
        name="title" 
        id="" 
        placeholder="Введи название"
    >
    <input 
        v-model="task.desc"
        class="form__input" 
        type="text" 
        name="desc" 
        id="" 
        placeholder="Введи описание"
    >
    <button 
        @click = "createTask"
        class="form__button" 
        type="submit">
        Добавить дело
    </button>
</form>
</template>

<style scoped>
  .form {
    display: flex;
    flex-direction: column;
    row-gap: 15px;
  }

  .form__input {
    margin: 0;
    padding: 0;
    border: 0;
    outline: none;

    padding: 10px;
    border-radius: 10px;
    background-color: rgb(241,255,207);

    font-size: 16px;
    line-height: 1.2;
    font-weight: 400;
  }

  .form__button {
    margin: 0;
    padding: 0;
    border: 0;
    outline: none;

    font-size: 16px;
    line-height: 1.2;
    font-weight: 700;

    padding: 10px;
    border-radius: 10px;
    background-color: rgb(241,255,207);
    transition: transform ease-in 0.7s;
  }

  .form__button:hover {
    transform: translateY(-2px);
    cursor: pointer;
  }
</style>