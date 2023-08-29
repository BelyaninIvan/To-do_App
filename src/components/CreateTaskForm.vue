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
            this.task.complete = false;
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
    <myInput
        v-model="task.title"
        placeholder="Введи название"
    />
    <myInput 
        v-model="task.desc"
        placeholder="Введи описание"
    />
    <myButton
      @click = "createTask"
    >
      Добавить дело
    </myButton>
</form>
</template>

<style scoped>
  .form {
    display: flex;
    flex-direction: column;
    row-gap: 15px;
  }
</style>